redmin
===
- docker-compose.yml
```yml
services:
  redmine:
    image: redmine:6.0.3
    restart: always
    ports:
      - "8008:3000"
    volumes:
      - ./redmine_files:/usr/src/redmine/files
    environment:
      REDMINE_DB_POSTGRES: db
      REDMINE_DB_USERNAME: redmine
      REDMINE_DB_PASSWORD: redmine
    depends_on:
      - db
 
  db:
    image: postgres:17.4-bookworm
    restart: always
    environment:
      POSTGRES_USER: redmine
      POSTGRES_PASSWORD: redmine
      POSTGRES_DB: redmine
    volumes:
      - ./pgdata:/var/lib/postgresql/data

```