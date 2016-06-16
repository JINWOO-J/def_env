REPO = dr.ytlabs.co.kr
NAME = elasticmq
VERSION = 0.9.3

.PHONY: all build push test tag_latest release ssh

all: build

build:
	docker build --no-cache --rm=true --build-arg ELASTICMQ_VERSION=$(VERSION) -t $(NAME):$(VERSION) .

push:
	docker tag -f $(NAME):$(VERSION) $(REPO)/$(NAME):$(VERSION)
	docker push $(REPO)/$(NAME):$(VERSION)

tag_latest:
	docker tag -f $(REPO)/$(NAME):$(VERSION) $(REPO)/$(NAME):latest
	docker push $(REPO)/$(NAME):latest
