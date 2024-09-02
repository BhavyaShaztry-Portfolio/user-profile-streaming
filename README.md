# User-Profile-Streaming | End-to-End Data Engineering Project
Brief Overview

In this project, I have used the Random User Generator API to fetch data intermittedly using Airflow DAG pipelines and store the data in Postgres DB. The entire streaming process is managed by a Kafka setup that has a Zookeeper pipeline to manage multiple broadcasts and process them from the message queue. There is a master-worker architecture setup on Apache Spark. Finally there is a Cassandra DB setup that has a listener that takes the stream data from Spark and stores in a columnar format. The entire project is containerized with Docker.

# System Architecture
![Data engineering architecture](https://github.com/user-attachments/assets/16aebf12-9085-44e0-8808-0a4c82408b8b)



The project is designed with the following components:

Data Source: We use randomuser.me API to generate random user data for our pipeline.
Apache Airflow: Responsible for orchestrating the pipeline and storing fetched data in a PostgreSQL database.
Apache Kafka and Zookeeper: Used for streaming data from PostgreSQL to the processing engine.
Control Center and Schema Registry: Helps in monitoring and schema management of our Kafka streams.
Apache Spark: For data processing with its master and worker nodes.
Cassandra: Where the processed data will be stored.

Setup and Requirements

1. Clone the repository
   
```git clone https://github.com/BhavyaShaztry-Portfolio/user-profile-streaming.git```

2. Navigate to the project directory

   ``` cd user-profile-streaming```

3. Run Docker Compose to Spin Up the Service
   
   ```docker-compose up```
