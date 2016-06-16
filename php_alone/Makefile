REPO = dr.ytlabs.co.kr
NAME = php
VERSION = 5.6.22

.PHONY: all build push test tag_latest release ssh

all: build

build:
	docker build --no-cache --rm=true --build-arg PHP_VERSION=$(VERSION) -t $(NAME):$(VERSION) .

push:
	docker tag -f $(NAME):$(VERSION) $(REPO)/$(NAME):$(VERSION)
	docker push $(REPO)/$(NAME):$(VERSION)

tag_latest:
	docker tag -f $(REPO)/$(NAME):$(VERSION) $(REPO)/$(NAME):latest
	docker push $(REPO)/$(NAME):latest
