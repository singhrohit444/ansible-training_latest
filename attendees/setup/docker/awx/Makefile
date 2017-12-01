build:
	docker build -t training/ansible:ubuntu -f Dockerfile.ubuntu .
	docker build -t training/ansible:centos -f Dockerfile.centos .

build-cserver:
	docker build -t training/ansible:cserver -f Dockerfile.cserver .

build-tserver:
	docker build -t training/ansible:tserver_centos -f Dockerfile.tserver.centos .
	docker build -t training/ansible:tserver_ubuntu -f Dockerfile.tserver.ubuntu .

build-all:
	make build
	make build-cserver
	make build-tserver

run-web-az-a:
	docker rm -f webaza || true
	docker run -h webaza --name webaza -itd training/ansible:tserver_ubuntu

run-web-az-b:
	docker rm -f webazb || true
	docker run -h webazb --name webazb -itd training/ansible:tserver_centos

run-app-az-a:
	docker rm -f appaza || true
	docker run -h appaza --name appaza -itd training/ansible:tserver_ubuntu

run-app-az-b:
	docker rm -f appazb || true
	docker run -h appazb --name appazb -itd training/ansible:tserver_centos

run-db-az-a:
	docker rm -f dbaza || true
	docker run -h dbaza --name dbaza -itd training/ansible:tserver_ubuntu

run-db-az-b:
	docker rm -f dbazb || true
	docker run -h dbazb --name dbazb -itd training/ansible:tserver_centos

run-control-server:
	docker rm -f cserver || true
	docker run -h cserver --name cserver --link webaza:webaza --link webazb:webazb --link appaza:appaza --link appazb:appazb --link dbaza:dbaza --link dbazb:dbazb -v `PWD`/..:/code -itd training/ansible:cserver /bin/bash

run-rabbitmq:
	docker rm -f rabbitmq || true
	docker run -itd --name rabbitmq -e RABBITMQ_DEFAULT_VHOST=awx rabbitmq:3

run-postgres:
	docker rm -f postgres || true
	docker run -itd --name postgres  -e POSTGRES_USER=awx -e POSTGRES_PASSWORD=awxpass -e POSTGRES_DB=awx postgres:9.6

run-memcached:
	docker rm -f memcached || true
	docker run -itd --name memcached memcached:alpine

run-awxweb:
	docker build -t training/ansible:awxweb -f Dockerfile.awxweb .
	docker rm -f awxweb || true
	docker run -itd --name awxweb --link rabbitmq:rabbitmq --link memcached:memcached --link postgres:postgres -p 80:8052 training/ansible:awxweb

run-awxtask:
	docker build -t training/ansible:awxtask -f Dockerfile.awxtask .
	docker rm -f awxtask || true
	docker run -itd --name awxtask --link rabbitmq:rabbitmq --link memcached:memcached --link postgres:postgres --link awxweb:awxweb training/ansible:awxtask

start-awx-lab:
	make run-rabbitmq
	make run-postgres
	make run-memcached
	make run-awxweb
	make run-awxtask

run-all:
	make run-web-az-a
	make run-web-az-b
	make run-app-az-a
	make run-app-az-b
	make run-db-az-a
	make run-db-az-b
	make run-control-server
	make start-awx-lab

start-lab:
	make build-all
	make run-all
