# Description
Start RabbitMQ with MQTT plugin installed

# Create a new docker image
```shell
docker build -t rabbitmq-mqtt .
```

# Start container
```shell
docker run -it --name rabbitmq -p 5672:5672 -p 15672:15672 -p 1883:1883 -p 15675:15675 rabbitmq-mqtt
```

- AMQP port 5672
- management web interface port 15672
- MQTT protocol port 1883
- WebSocket protocol port 15675

MQTT over WebSocket can be accessed at ws://localhost:15675/ws.

# Test
```shell
mosquitto_sub -t test
mosquitto_pub -t test -m 'Hello RabbitMQ'
```
