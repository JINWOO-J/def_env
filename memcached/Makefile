REPO = dr.ytlabs.co.kr
NAME = memcached
VERSION = 1.4.25

.PHONY: all build push test tag_latest release ssh bash

all: build push

build:
#	docker build --no-cache --rm=true --build-arg NGINX_VERSION=nginx-$(VERSION) -t $(REPO)/$(NAME):$(VERSION) .
	docker build --no-cache --rm=true --build-arg MEMCACHED_VERSION=$(VERSION) -t $(NAME):$(VERSION) .

push:
	docker tag -f $(NAME):$(VERSION) $(REPO)/$(NAME):$(VERSION)
	docker push $(REPO)/$(NAME):$(VERSION)

bash:
	docker run --entrypoint="bash" --rm -it $(NAME):$(VERSION)

tag_latest:
	docker tag -f $(REPO)/$(NAME):$(VERSION) $(REPO)/$(NAME):latest
	docker push $(REPO)/$(NAME):latest

test:
	docker run --rm -it $(NAME):$(VERSION)
