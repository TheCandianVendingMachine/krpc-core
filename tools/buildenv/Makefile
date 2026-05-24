.PHONY: build test deploy

VERSION=`cat VERSION.txt`

build:
	docker build \
	  --build-arg bazel_version=7.2.1 \
	  -t ghcr.io/thecandianvendingmachine/krpc-buildenv:$(VERSION) .

test:
	docker run -t -i ghcr.io/thecandianvendingmachine/krpc-buildenv:$(VERSION)

deploy:
	docker push ghcr.io/thecandianvendingmachine/krpc-buildenv:$(VERSION)
	docker tag ghcr.io/thecandianvendingmachine/krpc-buildenv:$(VERSION) ghcr.io/thecandianvendingmachine/krpc-buildenv:latest
	docker push ghcr.io/thecandianvendingmachine/krpc-buildenv:latest
