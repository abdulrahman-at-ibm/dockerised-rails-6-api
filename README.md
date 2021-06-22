# README

* Ruby version: ruby 3.0.1p64 (2021-04-05 revision 0fb782ee38) [x86_64-linux-musl]

* Rails version: 6.1.3.2

## System dependencies
* Docker
* Docker Compose
* Ruby 3.0.1

## How to get the application running:

1. Add environment variables
2. Build the containers
3. Create the database in the `web` container
4. Start the application


### 1: Configuration

Build the containers:
```sh
docker-compose build
```

### 2: Database creation

The database will be in a Docker container. Add the environment variables if you're doing a production build.

### 3: Database initialization

Create the Rails databases:
```sh
docker-compose run web bundle exec rails db:create
docker-compose run web bundle exec rails db:migrate
```

### 4: Run the test suite

Install RSpec:
```sh
docker-compose run web bundle exec rails generate rspec:install
```

Run the tests:
```sh
docker-compose run web bundle exec rspec
```

### 5: Start the Rails server

Start Rails:

```sh
docker-compose up --build
```

Go to `http://localhost:3000`


Sources: 
1. https://www.docker.com/get-started
2. https://docs.docker.com/compose/install/
3. https://yizeng.me/2019/11/09/setup-a-ruby-on-rails-6-api-project-with-docker-compose/
