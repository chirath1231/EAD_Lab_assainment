# EAD_Lab2_Submission
Contains a Lab submission for Enterprise Application Development Module

## Running the application

1. Create the database in MySQL:

   ```sql
   DROP DATABASE IF EXISTS library_db;
   CREATE DATABASE library_db;
   ```

2. Set your MySQL root password and start the application (PowerShell):

   ```powershell
   $env:DB_PASSWORD = "your_root_password"
   .\mvnw.cmd spring-boot:run
   ```

3. The API is at http://localhost:8080/api/books and Swagger UI is at http://localhost:8080/swagger-ui.html.

## Running with Docker Compose (Lab 03)

1. Copy `.env.example` to `.env` and set the MySQL root password:

   ```powershell
   Copy-Item .env.example .env
   ```

2. Build the JAR and start the API and MySQL containers:

   ```powershell
   .\mvnw.cmd clean package -DskipTests
   docker compose up --build -d
   docker compose ps
   ```

3. The API is at http://localhost:8080/api/books and Swagger UI is at http://localhost:8080/swagger-ui.html. The container database is on `localhost:3307`.

4. Stop the system with `docker compose down`. Add `-v` only to delete the database volume as well.
