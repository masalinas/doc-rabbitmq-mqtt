# Description
Start RabbitMQ with MQTT plugin installed

# Create a new docker image
Create a new rabbitMQ docker image from Dockerfile with the mqtt plugins installed:

```shell
docker build -t rabbitmq-mqtt .
```

# Start container
Start container executing this command with these ports opened:

```shell
docker run -it --name rabbitmq -p 5672:5672 -p 15672:15672 -p 1883:1883 -p 15675:15675 rabbitmq-mqtt
```

Ports List opened

- **Management Web UI:** 15672
- **MQTT protocol:** 1883
- **WebSocket protocol:** 15675
- **AMQP:** 5672

MQTT over WebSocket can be accessed at **ws://localhost:15675/ws**

# Test
Using mosquitto mqtt pub/sub clients to test mqtt connection

```shell
mosquitto_sub -t test
mosquitto_pub -t test -m 'Hello RabbitMQ'
```
