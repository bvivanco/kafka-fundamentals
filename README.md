# Fundamentos de Kafka
Kafka Fundamentals Course

## Primeros pasos con Docker
- Para levantar nuestros nodos en Docker:

docker compose -f <file.yml> up -d

- Para bajar los nodos en Docker :

docker compose -f <file.yml> down
 
 - Verificamos los containers creados:

docker ps
![image](https://user-images.githubusercontent.com/8194954/166873561-e2a28b37-35b9-4f65-a40c-86f8aa820899.png)

### Topics

- Creamos un topic en una Kafka Broker

/opt/bitnami/kafka/bin$ kafka-topics.sh --bootstrap-server 0.0.0.0:9091,0.0.0.0:9092,0.0.0.0:9093 --topic mx-transaction --create --rep
lication-factor 3 --partitions 3

![image](https://user-images.githubusercontent.com/8194954/166873387-d8a78854-cbd0-4f0d-ab36-f13a6fd9ca9f.png)

- Verificamos el topic creado
 
 kafka-topics.sh --bootstrap-server 0.0.0.0:9091,0.0.0.0:9092,0.0.0.0:9093 --topic mx-transaction --describe
 
![image](https://user-images.githubusercontent.com/8194954/166874062-731c59fc-5d9b-4286-a30f-5c74d1c5bf8a.png)

### Consumidores

- Creamos consumidores en una Kafka Broker por cada area

kafka-console-consumer.sh --bootstrap-server 0.0.0.0:9091,0.0.0.0:9092,0.0.0.0:9093 --topic mx-transaction --gr
oup finance
