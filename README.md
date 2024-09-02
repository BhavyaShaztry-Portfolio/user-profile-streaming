# User-Profile-Streaming | End-to-End Data Engineering Project
Brief Overview

In this project, I have used the Random User Generator API to fetch data intermittedly using Airflow DAG pipelines and store the data in Postgres DB. The entire streaming process is managed by a Kafka setup that has a Zookeeper pipeline to manage multiple broadcasts and process them from the message queue. There is a master-worker architecture setup on Apache Spark. Finally there is a Cassandra DB setup that has a listener that takes the stream data from Spark and stores in a columnar format. The entire project is containerized with Docker.

# System Architecture
![Data engineering architecture](https://github.com/user-attachments/assets/16aebf12-9085-44e0-8808-0a4c82408b8b)



The project is designed with the following components:

__Data Source__: We use ```randomuser.me``` API to generate random user data for our pipeline.<br/>
__Apache Airflow__: Responsible for orchestrating the pipeline and storing fetched data in a PostgreSQL database.<br/>
__Apache Kafka and Zookeeper__: Used for streaming data from PostgreSQL to the processing engine.<br/>
__Control Center and Schema Registry__: Helps in monitoring and schema management of our Kafka streams.<br/>
__Apache Spark__: For data processing with its master and worker nodes.<br/>
__Cassandra__: Where the processed data will be stored.

# Technologies
- Apache Airflow
- Python
- Apache Kafka
- Apache Zookeeper
- Apache Spark
- Cassandra
- PostgreSQL
- Docker
# Setup and Requirements

1. Clone the repository
   
```git clone https://github.com/BhavyaShaztry-Portfolio/user-profile-streaming.git```

2. Navigate to the project directory

   ``` cd user-profile-streaming```

3. Run Docker Compose to Spin Up the Service
   
   ```docker-compose up```

# Demo
# Apache Airflow DAG
![Screenshot (110)](https://github.com/user-attachments/assets/d2bd7af7-0075-40c6-a887-61d8d8a4b244)



# Confluent Control Center Consumption Stats and Health of Broker
![Capture](https://github.com/user-attachments/assets/f58411c3-aa34-4acc-84d3-999ba409c937)

# Confluent Control Center Message Queue
![Capture2](https://github.com/user-attachments/assets/c9ad9a91-a51d-4101-a0b5-00ec1fcf861d)

# Docker Containers
![Screenshot (112)](https://github.com/user-attachments/assets/83a7758b-8431-4b72-9432-cb23aee5f96f)




