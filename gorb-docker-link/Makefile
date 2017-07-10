all: push

# 0.0 shouldn't clobber any release builds
TAG = 0.0
PREFIX = test/gorb-docker-link

binary: main.go
	CGO_ENABLED=0 GOOS=linux  go build -a -ldflags '-w' -o docker/gorb-docker-link

container: binary
	docker build -t $(PREFIX):$(TAG) docker

push: container
	docker push $(PREFIX):$(TAG)

clean:
	rm -f docker/gorb-docker-link
