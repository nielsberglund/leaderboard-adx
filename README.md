# Stream Data from Kafka to Azure Data Explorer

This was originally the backing repo for the [**Develop a Real-Time Leaderboard Using Kafka and Azure Data Explorer - I**][1] blog-post, where I in the post cover - in some detail - how to "hook up" **Apache Kafka** and **Azure Data Explorer**. This `README.md` file pointed to the blog post, and nothing else. 

This repo is still the backing repo, and this file still points to the [post][1]. However, I have quite a few posts "out in the wild" talking about Kafka and ADX, and in each post I discuss to some degree how to set-up Kafka and ADX. I thought it would be beneficial if I summarized the details, and this `README.md` is that summary.

## Kafka

In case someone doesn't know what Kafka is: Apache Kafka is a distributed streaming platform. It is designed to handle large volumes of real-time data streams and enable real-time data processing and analysis. Kafka is built on top of the publish-subscribe messaging model, where producers publish messages to topics, and consumers subscribe to those topics to receive and process the messages. It uses a distributed architecture that allows it to scale horizontally across multiple servers and handle large amounts of data:

![Kafka](/leaderboard-adx/blob/main/assets/images/kafka-pub-sub.png)


## Azure Data Explorer

[Azure Data Explorer][2] is a fully managed data exploration service provided by Microsoft Azure. It is designed for big data scenarios and allows users to quickly and easily analyze large amounts of data using a SQL-like language. ADX can handle structured and unstructured data and can be used to perform tasks such as data exploration, real-time analytics, and visualization.

It uses a distributed columnar storage system and a query engine designed to handle complex queries and perform well even with massive datasets. Additionally, ADX uses advanced indexing and caching techniques to speed up queries and reduce the need for full table scans. It also allows for near real-time data ingestion and supports complex data types such as JSON and Avro.







It still is, but the `README.md` file (what you read now) is now expanded to cover more in detail how to set up **Azure Data Explorer** and **Kafka** to stream data from a Kafka topic to ADX. Essentially it summarizes what is in the [post][1]. 

This is the code repo for the [Develop a Real-Time Leaderboard Using Kafka and Azure Data Explorer - I][1].

The blog post explains what the code does.

[1]: https://nielsberglund.com/post/2023-03-19-develop-a-real-time-leaderboard-using-kafka-and-azure-data-explorer---i/
[2]: https://docs.microsoft.com/en-us/azure/data-explorer/
