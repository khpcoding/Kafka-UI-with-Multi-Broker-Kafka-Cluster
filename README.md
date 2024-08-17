# Kafka UI with Multi-Broker Kafka Cluster


This project sets up a multi-broker Kafka cluster along with a Kafka UI for managing and monitoring the cluster. The setup includes three Kafka brokers, a Zookeeper instance, and Kafka UI running on Docker.

### Prerequisites
- Docker installed on your machine
- Docker Compose installed on your machine
  
### Project Structure

The project is composed of the following services:

### 1. Kafka UI (kafka-ui):

 A user-friendly interface to manage and monitor Kafka clusters.

### 2. Zookeeper (zookeeper):

Used to coordinate and manage the Kafka brokers.

### 3. Kafka Brokers:

- `kafka1`: The first Kafka broker instance.
- `kafka2`: The second Kafka broker instance.
- `kafka3`: The third Kafka broker instance.

### Configuration

The Kafka cluster is configured with the following settings:

- Kafka UI is accessible at http://localhost:8080.
- Zookeeper is accessible at port 2181.
- Kafka Brokers are accessible on ports 9092, 9093, and 9094 for kafka1, kafka2, and kafka3 respectively.

### Environment Variables

The Kafka UI service has the following environment variables configured:
- `KAFKA_CLUSTERS_0_NAME`: Name of the Kafka cluster.
- `KAFKA_CLUSTERS_0_BOOTSTRAPSERVERS`: List of Kafka broker addresses.
- `KAFKA_CLUSTERS_0_ZOOKEEPER`: Zookeeper connection string.
  
### Kafka Brokers Configuration

Each Kafka broker is configured with:

- `KAFKA_ADVERTISED_HOST_NAME`: The hostname that Kafka advertises to clients.
- `KAFKA_ZOOKEEPER_CONNECT`: The Zookeeper connection string.
- `KAFKA_BROKER_ID`: A unique ID for the broker within the cluster.

### Getting Started
To start all the services, simply run the following command:

```bash
docker-compose up -d
```

This command will start the Kafka UI, Zookeeper, and the three Kafka brokers in detached mode.

### Stopping the Services
To stop the services, run:

```bash
docker-compose down
```
This will stop and remove the containers for all services.

### Accessing Kafka UI

Once the services are running, you can access the Kafka UI at `http://localhost:8080`. The UI provides a web interface for interacting with your Kafka cluster, allowing you to monitor topics, consumers, and messages.





