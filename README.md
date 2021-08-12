# QuickStartKafka
Apache Kafka® Quick Start

# Start Kafka Broker
docker-compose up -d

# Create a Topic
docker exec broker kafka-topics --bootstrap-server broker:9092 --create --topic quickstart
             
# Write messages to the topic
docker exec --interactive --tty broker kafka-console-producer --bootstrap-server broker:9092 --topic quickstart
                       
# Type in some text
this is my first kafka message
hello world!
this is my third kafka message. I’m on a roll :-D

# Read messages from the topic
docker exec --interactive --tty broker kafka-console-consumer --bootstrap-server broker:9092 --topic quickstart --from-beginning
 
# Write some more messages
docker exec --interactive --tty broker kafka-console-producer --bootstrap-server broker:9092 --topic quickstart

# Stop the Kafka broker
docker-compose down
