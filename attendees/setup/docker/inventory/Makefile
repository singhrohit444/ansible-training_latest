build:
	docker build -t training/ansible .

run-web-az-a:
	docker rm -f webaza || true
	docker run -h webaza --name webaza -itd training/ansible /bin/bash

run-web-az-b:
	docker rm -f webazb || true
	docker run -h webazb --name webazb -itd training/ansible /bin/bash

run-app-az-a:
	docker rm -f appaza || true
	docker run -h appaza --name appaza -itd training/ansible /bin/bash

run-app-az-b:
	docker rm -f appazb || true
	docker run -h appazb --name appazb -itd training/ansible /bin/bash

run-db-az-a:
	docker rm -f dbaza || true
	docker run -h dbaza --name dbaza -itd training/ansible /bin/bash

run-db-az-b:
	docker rm -f dbazb || true
	docker run -h dbazb --name dbazb -itd training/ansible /bin/bash

run-control-server:
	docker rm -f cserver || true
	docker run -h cserver --name cserver -itd training/ansible /bin/bash

run-all:
	make run-web-az-a
	make run-web-az-b
	make run-app-az-a
	make run-app-az-b
	make run-db-az-a
	make run-db-az-b
	make run-control-server
