---
{"dg-publish":true,"permalink":"//docker/compose-yaml/"}
---


一个例子：
services中包含了两个服务：server和db。其中，db 是 server 的依赖项。
```yaml
services:
  server:
    build:
      context: .
    ports:
      - 5000:5000
    environment: 
      - POSTGRES_PASSWORD=mysecretpassword
    depends_on:  # 当前服务的依赖项和要求
      db:
        condition: service_healthy
    develop:  # 开发选项
      watch:
        - action: rebuild   # 一旦文件被修改，就重新 build 应用
          path: .
  db:
    image: postgres
    restart: always
    user: postgres
    secrets:
      - db-password
    volumes:
      - db-data:/var/lib/postgresql/data
    environment:
      - POSTGRES_DB=example
      - POSTGRES_PASSWORD_FILE=/run/secrets/db-password
    expose:
      - 5432
    healthcheck:
      test: [ "CMD", "pg_isready" ]
      interval: 10s
      timeout: 5s
      retries: 5
volumes:
  db-data:
secrets:
  db-password:
    file: db/password.txt
```

[[工程向/Docker/docker-watch\|docker-watch]] 