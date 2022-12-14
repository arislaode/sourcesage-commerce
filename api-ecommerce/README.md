# Documentation
* Prequirement:
    - Python version 3.8.10
    - Flask version 2.0.1
    - Docker version 20.10.12
    - MySQL version 8.0.31

* Create environment
    ```bash
    pip install virtualenv
    ```
    ```bash
    virtualenv -p python3 env
    ```
* Active environment:
    ```bash
        source env/bin/activate
    ```

* Install all package needed
    ```bash
        pip install -r requirements.txt
    ```

* deactive environment via docker in .env file 
    ```bash
    # DB_HOST= "db-sql:3306"
    # DB_USERNAME= "user"
    # DB_PASSWORD= "password"
    # DB_NAME="db"
    ```

* Activate environment via local in .env 
    ```bash
        DB_HOST=localhost
        DB_USERNAME=your-db-username
        DB_PASSWORD=your-db-password
        DB_NAME=your-db-name
    ```

* Setup & Migrate Database 
  - create your database. In this project my database name : ecommerce 
  - export environment flaskk app 
    ```bash
        export FLASK_APP=main.py
    ```
  - create a migration repository
    ```bash
        flask db init
    ```
  - generate migration
    ```bash
        flask db migrate
    ```
  - Migrate script to your database
      ```bash
        flask db upgrade
    ```
* Running API
    -   Running app :
        ```bash
            bash boot.sh
        ```
    - Check your api at url http://127.0.0.1:8082

* Running via Docker
    - create docker image:
        ```bash
            docker build --tag api-commerce .
        ```

    - create docker container:
        ```bash
            docker run -d -p 8083:8080 --name api-commerce-app api-commerce
        ```

    - Check your api at url http://127.0.0.1:8083