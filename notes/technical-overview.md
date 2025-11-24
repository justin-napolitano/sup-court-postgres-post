---
slug: github-sup-court-postgres-post-note-technical-overview
id: github-sup-court-postgres-post-note-technical-overview
title: sup-court-postgres-post
repo: justin-napolitano/sup-court-postgres-post
githubUrl: https://github.com/justin-napolitano/sup-court-postgres-post
generatedAt: '2025-11-24T18:47:23.768Z'
source: github-auto
summary: >-
  This repo is all about integrating a Java application with a PostgreSQL
  database using Docker and Maven. It's a practical way to learn database
  interactions and schema management through SQL.
tags: []
seoPrimaryKeyword: ''
seoSecondaryKeywords: []
seoOptimized: false
topicFamily: null
topicFamilyConfidence: null
kind: note
entryLayout: note
showInProjects: false
showInNotes: true
showInWriting: false
showInLogs: false
---

This repo is all about integrating a Java application with a PostgreSQL database using Docker and Maven. It's a practical way to learn database interactions and schema management through SQL.

### Key Components
- **PostgreSQL** and **Adminer** via Docker
- **Maven** for project management
- SQL scripts for creating tables in the `sql/` directory

### Getting Started
1. Clone the repo:
   ```bash
   git clone https://github.com/justin-napolitano/sup-court-postgres-post.git
   cd sup-court-postgres-post
   ```
2. Run PostgreSQL and Adminer:
   ```bash
   docker-compose up -d
   ```

Make sure PostgreSQL is on port 5432 and Adminer on port 8080. Then, set up the Maven project and dependencies in `pom.xml`, and run:
```bash
mvn clean install
mvn exec:java -Dexec.mainClass="com.createdb.Main"
```

#### Gotchas
- Ensure JDK, Maven, Docker, and Docker Compose are installed beforehand.
