PROJECT_NAME = "PCR"

server-image:
	docker image build -t citi_project/pcr-server .


start: stop
	docker-compose -p $(PROJECT_NAME) up -d

stop:
	docker-compose -p $(PROJECT_NAME) down

create-migration:
	migrate.exe create -dir store/migrations -ext sql -seq -digits 2 <message>
