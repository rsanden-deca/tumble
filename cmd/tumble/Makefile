SHELL:=/bin/bash

BUILD_VERSION=0.1.211228a
BUILD_NAME=tumble
REPO_VERSION=$$(git rev-parse HEAD | head -c8)$$([[ $$(git diff | wc -c) = 0 ]] || echo '-d')

.PHONY: all clean exe test

all: exe

clean:
	rm -rf tmp
	rm -f VERSION.txt
	rm -f tumble

exe: clean
	echo "$(BUILD_NAME) v$(BUILD_VERSION)-$(REPO_VERSION)" > VERSION.txt
	go build

test: exe
	go test -parallel 1
