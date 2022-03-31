compose_file := docker-compose.ducx.yaml
compose := docker-compose -f $(compose_file)
tail := 1000

build:
	$(compose) build --parallel

up_db:
	$(compose) up -d db

up:
	$(compose) up -d

up_service:
	$(compose) up -d $(service)

up_build: build
	$(compose) up -d

up_service_build: build
	$(compose) up -d $(service)

down:
	$(compose) down

ps:
	$(compose) ps -a $(service)

logs:
	$(compose) logs --timestamps --tail $(tail) -f $(service)

pull_git:
	git pull origin DUCXv2

pull_docker:
	$(compose) pull

pull: pull_git pull_docker
