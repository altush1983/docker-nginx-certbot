# If we have `--squash` support, then use it!
ifneq ($(shell docker build --help 2>/dev/null | grep squash),)
DOCKER_BUILD = docker build --squash
else
DOCKER_BUILD = docker build
endif

all: build

build: Makefile Dockerfile
	$(DOCKER_BUILD) -t docker.altush.ru/nginx-certbot:v1.1 .
	@echo "Done!  Use docker run docker.altush.ru/nginx-certbot:v1.1 to run"

push:
	docker push docker.altush.ru/nginx-certbot
