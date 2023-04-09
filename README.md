# From Kafka to Amazon S3: Partitioning Outputs
This repository contains the source code for my blog post From Kafka to Amazon S3: Partitioning Outputs

This is a tutorial on creating a pipeline that streams data from Kafka topic onto AWS S3 bucket with help of Kafka Connect.

You can find the full description of how to set the environment and run it in the post.

This tutorial is divided into three parts, each covering a different aspect of streaming data with Kafka Connect. In the first part, we will explore how to stream simple JSONs using the DefaultPartitioner, which preserves the default Kafka topic partitions. In the second part, we will dig into more advanced partitioning techniques by using FieldPartitioner and TimeBasedPartitioner to create partitions by selected field or timestamp. Finally, in the third part, we will use Confluent Schema Registry to stream binary data in Protobuf format and convert it to Parquet on the fly. By the end of this tutorial, you will have a good understanding of different partitioning techniques and how to use them in your Kafka streaming applications.


  ![Containers](https://cdn-images-1.medium.com/max/1600/1*T4VSyNGtld6cfYCIwgsLTw.png)

## DefaultPartitioner

    docker-compose -f docker-compose.yml -f local/json-nonpartitioned-to-json/docker-compose.yml up -d

## FieldPartitioner

    docker-compose -f docker-compose.yml -f local/json-partitioned-to-json/docker-compose.yml up -d

## TimeBasedPartitioner

    docker-compose -f docker-compose.yml -f local/json-partitioned-to-json/docker-compose-time.yml up -d

## Confluent Schema Registry, Protobuf and Parquet

  ![Containers](https://user-images.githubusercontent.com/14594349/230781419-6d2cb3a1-1527-4793-bce2-d6a593feb426.png)
  
    docker-compose -f docker-compose.yml  -f local/json-schema-registry/docker-compose.yml up -d
