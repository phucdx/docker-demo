- Build docker-compose

```
docker-compose build
```

- Create Rails app

```
docker-compose run app rails new . --force --database=mysql
```

- By default docker runs with root user, so need to grant permission for new files/folders

```
sudo chown $USER:$USER -R .
```

- Config `config/database.yml`

```
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: <%= ENV.fetch("DATABASE_USER_NAME") %>
  password: <%= ENV.fetch("DATABASE_PASSWORD") %>
  host: <%= ENV.fetch("DATABASE_HOST") %>
```

- Up docker-compose

```
docker-compose up
```

- Access to `http://localhost:3002`
