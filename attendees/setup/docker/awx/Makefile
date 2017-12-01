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

start-lab:
	make run-rabbitmq
	make run-postgres
	make run-memcached
	make run-awxweb
	make run-awxtask
