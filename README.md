# Data-Engineer-Notes

# SQL
- Declarative language used to store and query structure data.
- A common interface for database and data lakes
- Underrated. Transactional properties make it fast and powerful to use.

```
## Advanced SQL (need to know)

# GROUP BYs to aggregate values
SELECT
  MAX (views) AS mostViews,
  channelID
FROM
  YoutubeVideos
GROUP BY
  channelID
;

# Window functions for interviews

SELECT
  RANK() OVER(ORDER BY views) AS videoRanking
  videoName,
FROM
  YoutubeVideos
;

# Efficient schema designs go a long way
CREATE TABLE YoutubeVideos (
  videoID INTEGER PRIMARY KEY
  videoName VARCHAR(255),
  views INTEGER,
  likes INTEGER,
  channelID INTEGER
);
```
Python

- Key for reproducibility is ISOLATED for EACH SYSTEM
- Common tools : Pandas, NumPy, sci-kit learn, TensorFlow, PySpark

Commmand Lines
-Working on remote machines often will require this skill
-Moving around files, searching through logs, version control - useful for building an Extract Transform Load (ETL) pipeline
-CL help facilitate that interaction and improve developer productivity

Core Skills

# Data Storage

- Storage underpins every aspect of Data Engineering - ingestion, transformation, queries
- Many Cloud Computing Services (AWS, GCP, Azure)

| Storage             | Description                                                 |
|---------------------|-------------------------------------------------------------|
| Object Stores       | - Gold standard for data lakes                             |
|                     | - Inherently key-value stores                              |
|                     | - Ideal for unstructured data such as images, audio, text  |
| Relational Databases | - The most widely spread DB in the world (e.g. SQLite!) |
|                     | - Often the solution to most Data Engineering problems     |
|                     | - Extremely fast look-up time                              |

Object Stores using AWS S3

storing CSV     's3://testfile/frank.csv'
Bucket name is   'testfile'   and our key is   'frank.csv'
Tons of useful info stored: versioning, metadata, backups

# Data Orchestration

- The process of getting data into a Data Warehouse is called Extract Transformn Load (ETL)
- Used to schedule jobs at specific cadence ( minutes, days, weeks) for tasks (ingestion, processing, trasforming)
    - Data Provenance. " Where did this data originate from?"
    - Directed Acyclical Graphs (DAGs) help us organize workflowsprogramatically
- Apache Airflow is the gold standard in the industry
    - Design complex ETL task
    - Loggin capabilites
    - Sleek UI for visualization


Goals for learning

- Focus on learning concepts and building projects (couple of months or more as needed)
- Read overview : AWS S3 ; PostgreSQL;  Airflow

    - Project Goal: Create an Airflow DAG that extracts data from a favorited source (finance, agriculture, etc.) and upload into a Data Warehouse (any relational database).
 
    - Advanced Data Skills
 
 # Batch and Stream Processing
 
## Batch Processing
- Batch processing is heavily intertwined with Data Processing technologies. Apache Spark is often regarded as the gold standard in this area.

- The core idea of batch processing is to process data at unimaginable sizes using scalable tools. A common paradigm used for this purpose is MapReduce.

    - Map: This operation splits data between parallel tasks.
     - Reduce: This operation aggregates data.

Note that the order of the operations does not matter in the context of MapReduce.

- There is readily available cloud infrastructure for batch processing such as Amazon EMR and Databricks. The focus should be on understanding the concepts and creating projects using suitable tools. Tools and technologies may change over time, but mastering the concepts will always remain key.

## Stream Processing:
- Stream Processing is essential for building real-time applications where multiple sources feed into the system. It often utilizes a Publish and Subscribe (Pub/Sub) model, where producers publish messages to topics.

- Apache Kafka is one of the most popular frameworks for stream processing. It offers high throughput, capable of processing millions of messages per second. Moreover, it provides high scalability with support for thousands of brokers and maintains an immutable commit log.

- A real-world example of stream processing is Netflix. Netflix uses Apache Kafka for its messaging and streaming needs, processing billions of data points daily with Kafka.

As with batch processing, it's important to remember that tools and technologies in stream processing can also evolve over time. Thus, the focus should be on understanding the principles and applying the most appropriate solutions to problems.
