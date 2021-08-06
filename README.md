# QuickStartKafka
Apache Kafka® Quick Start

1) Start Kafka Broker
docker-compose up -d

2) Create a Topic
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --create \
             --topic quickstart
             
3) Write messages to the topic
docker exec --interactive --tty broker \
kafka-console-producer --bootstrap-server broker:9092 \
                       --topic quickstart
                       
4) Type in some text
this is my first kafka message
hello world!
this is my third kafka message. I’m on a roll :-D

5) Read messages from the topic
docker exec --interactive --tty broker \
kafka-console-consumer --bootstrap-server broker:9092 \
                       --topic quickstart \
                       --from-beginning
 
6) Write some more messages
docker exec --interactive --tty broker \
kafka-console-producer --bootstrap-server broker:9092 \
                       --topic quickstart

7) Stop the Kafka broker
docker-compose down
