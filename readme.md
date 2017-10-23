## Setup

Copy and rename the `docker-compose.yml.dist` to `docker-compose.yml`

Replace the `[YOUR IP ADDRESS]` in the `docker-compose.yml` file to your ip address.

Kafka:
```bash
docker-compose up -d
```

RabbitMQ:
```bash
docker-compose -f docker-compose.rabbit.yml up -d
```

Both containers have: PhpMyAdmin and RedisCommadner.

* PhpMyAdmin: [http://localhost:8081](http://localhost:8081)
* RedisCommander: [http://localhost:8082](http://localhost:8082)

For RabbitMQ, we have a management client: [http://localhost:8083](http://localhost:8083)

##### Troubleshot

Grant access to database:

```
GRANT ALL on maxwell.* to 'maxwell'@'%' identified by 'XXXXXX';
GRANT SELECT, REPLICATION CLIENT, REPLICATION SLAVE on *.* to 'maxwell'@'%';
```