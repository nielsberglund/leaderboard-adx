# Stream Data from Kafka to Azure Data Explorer

This was originally the backing repo for the [**Develop a Real-Time Leaderboard Using Kafka and Azure Data Explorer - I**][1] blog-post, where I in the post cover - in some detail - how to "hook up" **Apache Kafka** and **Azure Data Explorer**. This `README.md` file pointed to the blog post, and nothing else. 

This repo is still the backing repo, and this file still points to the [post][1]. However, I have quite a few posts "out in the wild" talking about Kafka and ADX, and in each post I discuss to some degree how to set-up Kafka and ADX. I thought it would be beneficial if I summarized the details, and this `README.md` is that summary.

## Kafka

In case someone doesn't know what Kafka is: Apache Kafka is a distributed streaming platform. It is designed to handle large volumes of real-time data streams and enable real-time data processing and analysis. Kafka is built on top of the publish-subscribe messaging model, where producers publish messages to topics, and consumers subscribe to those topics to receive and process the messages. It uses a distributed architecture that allows it to scale horizontally across multiple servers and handle large amounts of data:

![Kafka](/assets/images/kafka-pub-sub.png)

**Figure 1:** *Kafka*

You see in *Figure 1* what is mentioned above: in the middle you have a Kafka cluster (in this case three nodes), where the topics are distributed over the nodes. At the left you have multiple publishers, publishing events to topics in the Kafka cluster. On the right you have consumers, consuming these events from topics.

The consumers processes the events, and it may so be that the consumers write the events to other systems.

### Kafka Connect

Above I mentioned that consumers may write the events to other systems. Instead of having consumers writing explicit code for writing events to other systems, you can use Kafka Connect.

Kafka Connect is a framework that enables the integration of external systems with Apache Kafka. It provides a scalable and fault-tolerant way to stream data between Kafka topics and other data sources or sinks.

Kafka Connect consists of two main components:

* Connectors: A connector is a plugin that connects to an external system and defines the configuration and operations required to read from or write to that system. Connectors can be developed and installed independently of Kafka Connect.

* Connect worker: A connect worker is a Java process that manages the execution of connectors, including scaling, failover, and parallel processing of data. The connect worker runs on a separate machine or cluster from Kafka brokers and coordinates the data flow between connectors and Kafka.

Kafka Connect supports a wide range of connectors, including database connectors, file connectors, messaging system connectors, and cloud service connectors. By leveraging connectors, data can be easily and efficiently ingested into Kafka from a variety of sources or pushed from Kafka to other data stores or systems:

![Kafka Connect](/assets/images/kafka-connect.png)

**Figure 2:** *Kafka Connect*





## Azure Data Explorer

[Azure Data Explorer][2] is a fully managed data exploration service provided by Microsoft Azure. It is designed for big data scenarios and allows users to quickly and easily analyze large amounts of data using a SQL-like language. ADX can handle structured and unstructured data and can be used to perform tasks such as data exploration, real-time analytics, and visualization.

It uses a distributed columnar storage system and a query engine designed to handle complex queries and perform well even with massive datasets. Additionally, ADX uses advanced indexing and caching techniques to speed up queries and reduce the need for full table scans. It also allows for near real-time data ingestion and supports complex data types such as JSON and Avro.







It still is, but the `README.md` file (what you read now) is now expanded to cover more in detail how to set up **Azure Data Explorer** and **Kafka** to stream data from a Kafka topic to ADX. Essentially it summarizes what is in the [post][1]. 

This is the code repo for the [Develop a Real-Time Leaderboard Using Kafka and Azure Data Explorer - I][1].

The blog post explains what the code does.

[1]: https://nielsberglund.com/post/2023-03-19-develop-a-real-time-leaderboard-using-kafka-and-azure-data-explorer---i/
[2]: https://docs.microsoft.com/en-us/azure/data-explorer/
