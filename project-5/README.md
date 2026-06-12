# Project 5: Database Container with Docker

## Objective

The objective of this project is to learn how to run a MySQL database inside a Docker container and preserve data using Docker Volumes. This project demonstrates how data can survive container stops, removals, and recreations.

---

## Technologies Used

* Docker
* MySQL
* Docker Volumes

---

## Project Overview

In this project, a MySQL database container was deployed using Docker. Environment variables were used to configure the database, and a Docker volume was attached to store database files persistently. A database and table were created, records were inserted, and data persistence was verified after recreating the container.

---

## Steps Performed

### 1. Pulled the MySQL Image

Downloaded the official MySQL image from Docker Hub.

### 2. Created a Docker Volume

Created a Docker volume to store MySQL data outside the container filesystem.

### 3. Started the MySQL Container

Configured the container using environment variables:

* Root password
* Database name
* Username
* User password

Attached the Docker volume and exposed the MySQL port.

### 4. Verified Container Status

Checked that the MySQL container was running successfully.

### 5. Accessed the Database

Entered the container and connected to the MySQL server.

### 6. Created a Table

Created a table named `students` with the following columns:

* id
* name
* age

### 7. Inserted Records

Added sample records into the table.

| ID | Name  | Age |
| -- | ----- | --- |
| 1  | Ravi  | 20  |
| 2  | Priya | 21  |
| 3  | Arun  | 22  |

### 8. Viewed Records

Queried the table and verified that all records were stored successfully.

### 9. Tested Data Persistence

* Stopped the container
* Started the container again
* Verified that the database and records still existed

### 10. Recreated the Container

Removed the container while keeping the Docker volume.

Created a new MySQL container using the same volume and confirmed that all data was still available.

---

## Important Commands Used

### Pull MySQL Image

```bash
docker pull mysql
```

### Create Docker Volume

```bash
docker volume create mysql-volume
```

### Run MySQL Container

```bash
docker run -d \
--name mydb \
-v mysql-volume:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=admin \
-e MYSQL_DATABASE=student \
-e MYSQL_USER=priya \
-e MYSQL_PASSWORD=priya123 \
-p 3306:3306 \
mysql
```

### Verify Running Containers

```bash
docker ps
```

### Access Container Shell

```bash
docker exec -it mydb bash
```

### Connect to MySQL

```bash
mysql -u root -p
```

### Show Databases

```sql
SHOW DATABASES;
```

### Use Database

```sql
USE student;
```

### Create Students Table

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```

### Insert Records

```sql
INSERT INTO students VALUES
(1, 'Ravi', 20),
(2, 'Priya', 21),
(3, 'Arun', 22);
```

### View Records

```sql
SELECT * FROM students;
```

### Stop Container

```bash
docker stop mydb
```

### Start Container

```bash
docker start mydb
```

### Remove Container

```bash
docker rm -f mydb
```

### Recreate Container Using Existing Volume

```bash
docker run -d \
--name mydb-new \
-v mysql-volume:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=admin \
-p 3306:3306 \
mysql
```

### Verify Available Volumes

```bash
docker volume ls
```

## Skills Learned

* Running database containers
* Docker volumes
* Data persistence
* Environment variables
* Container lifecycle management
* MySQL administration basics
* SQL commands (CREATE, INSERT, SELECT)

---

## Results

* Successfully deployed a MySQL database using Docker.
* Configured the database using environment variables.
* Stored database data in a Docker volume.
* Verified that data remained available after container restart.
* Verified that data remained available after container removal and recreation.

---

## Conclusion

This project demonstrated how Docker volumes provide persistent storage for database containers. By storing MySQL data in a Docker volume, the database and records remained intact even after removing and recreating containers. This is an essential concept for managing stateful applications in Docker.
