---
slug: github-sup-court-postgres-post
title: Setting Up PostgreSQL with Java and Maven Using Docker Compose
repo: justin-napolitano/sup-court-postgres-post
githubUrl: https://github.com/justin-napolitano/sup-court-postgres-post
generatedAt: '2025-11-23T09:41:41.833249Z'
source: github-auto
summary: >-
  Reference for integrating PostgreSQL with Java via Maven, using Docker Compose and modular SQL
  scripts to enable scalable data workflows.
tags:
  - postgresql
  - java
  - maven
  - docker-compose
  - database-setup
seoPrimaryKeyword: postgresql java maven setup
seoSecondaryKeywords:
  - docker compose
  - database connectivity
  - sql scripts
seoOptimized: true
---

# Setting Up PostgreSQL with Java and Maven: A Technical Reference

This project documents the process of setting up a PostgreSQL database environment and integrating it with a Java application using Maven. The motivation stems from the need to build scalable, automated workflows for analyzing supreme court case data, moving beyond the limitations of off-the-shelf tools like DataShare.

## Motivation and Problem Statement

The initial exploration involved using DataShare for data analysis, which proved insufficient for the complexity and scale of the intended workflows. The goal is to develop a more versatile and scalable system by leveraging Java for application development and PostgreSQL for reliable data storage and querying.

## Project Setup

### Database Environment

PostgreSQL is deployed using Docker Compose alongside Adminer, a lightweight web-based database management tool. This setup allows for rapid initialization and management of the database without manual installation steps.

The `docker-compose.yml` file defines two services:

- `db`: Runs the latest PostgreSQL image with environment variables for user, password, and database name. It exposes port 5432 and persists data using a Docker volume.
- `adminer`: Runs the Adminer image, exposing port 8080 for browser-based database management.

Starting these services is done with `docker-compose up -d`, enabling a consistent and reproducible environment.

### Java and Maven Project Structure

The Java application follows a standard Maven directory layout:

- Source code resides in `src/main/java/com/createdb/`, containing `DatabaseClient.java` for database connectivity and `Main.java` as the application entry point.
- SQL scripts defining the database schema are stored in the `sql/` directory, including tables such as `CallNumbers`, `Contributors`, `Items`, `Resources`, and `Subjects`.
- The `pom.xml` file manages project dependencies, notably the PostgreSQL JDBC driver required for database communication.

### Database Connectivity

`DatabaseClient.java` likely encapsulates connection management, executing SQL scripts to create tables and perform queries. This abstraction facilitates interaction with the database while isolating connection details.

## Implementation Details

- The use of Docker Compose ensures that the database environment is portable and easily reproducible across different machines.
- SQL scripts are separated from application code, promoting modularity and ease of schema updates.
- Maven manages dependencies and build lifecycle, streamlining compilation and execution.
- The project assumes familiarity with Java and Maven, and requires Docker for containerized database setup.

## Practical Notes

- Running `docker-compose up -d` initializes the database and Adminer; Adminer can be accessed via `http://localhost:8080` for manual inspection.
- The PostgreSQL JDBC driver must be declared in `pom.xml` to allow Java code to connect to the database.
- SQL scripts should be executed in order to establish the necessary tables before running application logic.
- The project structure supports incremental development and testing of database interactions.

## Summary

This repository serves as a foundational reference for integrating Java applications with PostgreSQL databases using Docker and Maven. It emphasizes reproducible environment setup, modular schema management, and clear separation between application code and database definitions. The approach lays groundwork for building scalable data workflows and complex applications requiring robust data storage solutions.

