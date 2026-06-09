# WordPress Docker Project

## Overview

This project deploys a WordPress website using Docker containers with a MySQL database backend. The application is exposed on port 8080.

## Technologies Used

* Docker
* Docker Compose
* WordPress
* MySQL
* Apache
* Git & GitHub

## Project Architecture

WordPress Container (wp)
|
|
v
MySQL Container (mydb)

## Prerequisites

Install:

* Docker
* Docker Compose

Verify installation:

docker --version
docker compose version

## Project Files

.
├── docker-compose.yml
├── .env.example
├── wordpress_backup.sql
├── README.md

## Setup

### Clone Repository

git clone <repository-url>

cd wordpress-docker-project

### Create Environment File

Copy:

cp .env.example .env

Update credentials inside .env.

### Start Containers

docker compose up -d

### Verify Containers

docker ps

Expected containers:

* wp
* mydb

### Access Application

Open:

http://localhost:8080

or

http://SERVER_IP:8080

## Database Restore

If a backup file is provided:

docker cp wordpress_backup.sql mydb:/tmp/

docker exec -it mydb mysql -u root -p

Inside MySQL:

CREATE DATABASE mydb;

USE mydb;

SOURCE /tmp/wordpress_backup.sql;

## Stop Containers

docker compose down

## Remove Containers and Volumes

docker compose down -v

## Author

Dishant Panchal

