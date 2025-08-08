# Introduction to Apache Spark

Apache Spark is an open-source, distributed computing system designed for fast and flexible large-scale data processing. It supports batch and real-time analytics and provides APIs in Python, Java, Scala, and R.

## Key Features

- **Speed**: In-memory computation for fast processing.
- **Ease of Use**: High-level APIs in multiple languages.
- **Advanced Analytics**: Supports SQL, streaming, machine learning, and graph processing.
- **Scalability**: Handles petabytes of data across clusters.
- **Integration**: Works with Hadoop, HDFS, Hive, HBase, and more.

## Installation

Follow the [official guide](https://spark.apache.org/downloads.html) to download and set up Spark.

## Basic Example (PySpark)

```python
from pyspark.sql import SparkSession

# Initialize Spark session
spark = SparkSession.builder.appName("example").getOrCreate()

# Create DataFrame
data = [("Alice", 34), ("Bob", 45), ("Cathy", 29)]
df = spark.createDataFrame(data, ["Name", "Age"])

# Show DataFrame
df.show()

# Run SQL query
df.createOrReplaceTempView("people")
result = spark.sql("SELECT Name FROM people WHERE Age > 30")
result.show()