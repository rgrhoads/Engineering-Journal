# Creating Docker App
- [ ] Create docker-compose.yml file

- [ ] Add dbdump and

- [ ] ```javascript
    docker compose up
  ```
  - ```javascript
    version: '3.9'

    services:
      server:
        build:
          context: .
          dockerfile: Dockerfile
        restart: unless-stopped
        ports:
          - '3000:3000'
        deploy:
          replicas: 1
          restart_policy:
            max_attempts: 3
            condition: on-failure
          update_config:
            parallelism: 3
            delay: 10s
      db:
        image: 'postgres'
        ports:
          - '5432:5432'
        volumes:
          - ./dbdump:/docker-entrypoint-initdb.d
        environment:
          POSTGRES_PASSWORD: password123
          POSTGRES_USER: 'rgrhoads'
  ```