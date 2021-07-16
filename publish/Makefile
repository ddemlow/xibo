# Checks required environment variables
-include env.check.mk

export ARCH ?= $(shell hzn architecture)

all: publish publish-pattern-xibo

publish: publish-mysql publish-xmr publish-cms publish-memcached publish-ianw

publish-mysql:
	make -C src/mysql publish-service

publish-xmr:
	make -C src/xmr publish-service

publish-cms:
	make -C src/cms publish-service

publish-memcached:
	make -C src/memcached publish-service

publish-ianw:
	make -C src/ianw publish-service

publish-pattern-xibo:
	hzn exchange pattern publish -f horizon/xibo.pattern.json
