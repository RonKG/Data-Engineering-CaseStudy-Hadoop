Minimum Requirements:

- Apache Hadoop 3.0.1 

- Running Apache Ambari - Hortonworks on Linux

- JavaSE 1.8

- MySQL

- JDBC Java Connector 5.1.47


This project is a demonstartion of relevant ETL skills utilizing various tools in the Hadoop echo system. This work builds on a previous project - '[Data-Engineering-Java-MySQL](https://github.com/RonKG/Data-Engineering-Java)' - where data is retrieved from the MySQL RDBMS into Hadoop's **HDFS** for data warehousing.

#### The workflow and tools to achieve the above task is as follows:

1. Import data from MySQL with **SCOOP** using a scoop job running from the scoop meta-store. This is done with the use of scoop scripts.

2. Use **HIVE** scripts to create external tables that allow us a view into the imported data. A further managed table is also created and partitioned using one of the columns. This will allow us to improve the maintenance, performance or management of data.

3. The above two steps are bundled into an **OOZIE** Workflow. An oozie workflow allows us to schedule hadoop database tasks to run after a set of conditions are met.

4. Write additional Sqoop jobs to fetch new data from the RDBMS as appends or updated records.

5. This new  sqoop jobs are incorporated into a second Oozie workflow  and Coordinator files that handle the scheduled database updates on a regular bases.

6. This new data is visualized in Hive and resulting graphics can be found in the visuals folder of this repo.

