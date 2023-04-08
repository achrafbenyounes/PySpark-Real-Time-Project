# PySpark-Real-Time-Project
End to End PySpark Real Time Project Implementation.

Projects uses all the latest technologies - Spark, Python, PyCharm, HDFS, YARN, Google Cloud, AWS, Azure, Hive, PostgreSQL.

This project aims to understand the business Model and project flow of a USA Healthcare project.

Below is the project flow and explanation of its architecture : 

<img width="278" alt="image" src="https://user-images.githubusercontent.com/6604847/230717988-88fe04d6-00b0-4a03-b5ee-b7139394f7eb.png">

# Explanation of the above data pipeline : 

1- Data Ingestion: Bring row data into the system (HDFS, Spark DataFrame) from different sources (different relational databases, different file systems like CSV, Avro, Parquet, ORC, SAS Applications etc.).

2- Data Pre-Processing: Includes operations of cleansing the data.

3- Transformation: Is the core of any data pipeline project, refers to the operations that change the data, which may include data standardization, Sorting, Deduplication, Validation, Adding new columns, Dropping existing columns. The ultimate goal of this step is to make it possible to analyse the data.

4- Storage: In this step, we're going to persist the final transform data at some relational database or cloud services like S3 Bucket, Azure Blob etc.

<img width="584" alt="image" src="https://user-images.githubusercontent.com/6604847/230718086-17652101-8393-4cea-a0c4-9362673df726.png">

- run_pipeline.py: It's the pipeline script which is the execution starting point, this script will perform a series of operation, starting with ingestion data, data pre-processing and transforming data, data storage and data transfer. All we need to do is to execute the run_pipeline.py and that will trigger the other processes. See the picture above.


<img width="566" alt="image" src="https://user-images.githubusercontent.com/6604847/230718114-724e8799-ca9e-47d9-b3c9-8d05e4983e1e.png">

Let's analyse the data ingestion stage, in this step we will insert the vendor data into PySpark DataFrame.

The vendor data could be in different file formats like CSV, Parquet, ORC. The first task consists of bring data to the local server and from there we would copy it to our HDFS, from HDFS, we would load it to PySpark DataFrame.

This is the flow of Data Ingestion, and we're going to implement all these changes into a script. 

<img width="536" alt="image" src="https://user-images.githubusercontent.com/6604847/230718126-cc9e2692-5fc6-4599-8bd7-1a90e99dff23.png">

The next step in the pipeline is the data pre-processing, where we will do some data cleansing operations, we can have one or more data pre-processing operations.

After this, we'll have a series of transformations to modify the row of data into a final layout which make the data ready for analysing purpose.

<img width="428" alt="image" src="https://user-images.githubusercontent.com/6604847/230718148-c4497d8d-05ba-498f-b147-a21cf4f7d462.png">

In the next step, we would persist the data into Hive table and PostgreSQL database

<img width="505" alt="image" src="https://user-images.githubusercontent.com/6604847/230718168-53b19144-e19f-4dc1-ac7a-e461a6c92077.png">

Also we will transfer the final files to client's S3 Bucket, Azure blob and also to a Linux Path

<img width="527" alt="image" src="https://user-images.githubusercontent.com/6604847/230718242-9e58e232-1ed8-4c18-b56d-ee6371861881.png">

Througout this process will make sure that all the scripts should have a good Exception handling mechnisme and good logging mechanism

Below is an overview of some transormations : 


<img width="485" alt="image" src="https://user-images.githubusercontent.com/6604847/230718341-621d2771-3dd3-424d-a4af-71b832752ee1.png">




<img width="570" alt="image" src="https://user-images.githubusercontent.com/6604847/230718360-21b79beb-c77f-4ccc-9762-61d3a9281a6b.png">












