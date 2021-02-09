## Introduction <a name="introduction"></a>

Every organization desires to grow.

When an organization grows, it means a large audience interaction, many database requests, and longer response times. 

The overall impact will be a higher cost for resources. 

One of the best ways to solve these problems is by ensuring that database requests are served faster. 

If you're not good in IT, you may think that data can only be saved in a database, which is not true. 

A technique called "Caching" can help organizations to save time when serving database requests. 

In this article, we will discuss a popular Caching tool called "Redis".  

But before discussing more about Redis, let me first help you understand the process of Caching in depth. 

## Table of Contents

You can skip to a specific section of this tutorial using the table of contents below:

[Introduction](#introduction)

[What is Caching?](#caching)

[What is Redis?](#redis)

[Redis Features](#features)

- [Redis Sentinel](#sentinel)

- [Redis Cluster](#cluster)

- [Redis Pub/Sub](#pub)

- [Redis Persistence](#persistence)

[Redis Commands](#commands)

- [Setting a Key](#set)

- [Getting a Key](#get)

- [Deleting a Key](#delete)
	
- [Setting Keys with Expiry](#expiry)

- [Removing Key Timeout](#remove)
	
- [Renaming a Key](#rename)	

- [Flushing Contents](#flush)

[Conclusion:](#conclusion)

## What is Caching? <a name="caching"></a>

Caching refers to the process of storing some data in a "Cache". 

A Cache is a temporary storage area that stores data so that it can be accessed faster in future. 

It takes a shorter period of time to access data stored in a cache than data stored in a database. 

Web browsers normally cache JavaScript, HTML files, and images so as to load web pages more quickly. 

In caching, the data is stored in a fast access hardware like the RAM and it may be in correlation with a software component. 

## What is Redis? <a name="redis"></a>

Redis (REmote DIctionary Server) is an open source, fast, in-memory, key-value data store that is used as a database, cache, queue, and message broker. 

Redis supports various data structures like Hashes, Strings, Sets, Lists, etc. 

Due to this, Redis is referred to as a data structure server since its core data structures are similar to those provided by other programming languages. 

It also comes with other features and data structures for stream processing, geolocation, and approximate counting. 

Redis delivers sub-millisecond response times, supporting up to millions of requests per second for real-time applications in Financial Services, AdTech, IoT, Gaming, and Healthcare. 

When an application is getting data from external sources, the throughput and latency of data sources can cause a performance bottleneck, especially when the application scales or traffic increases. 

In such a case, one of the ways to improve performance is to store and modify the data in-memory, and that is exactly what Redis helps you achieve. 

Redis stores all its data in-memory, providing the fastest possible speed when writing or reading data, and it has built-in replication capabilities that allow you to place data physically closer to the user.

Other features that characterize Redis are high availability, multiple levels of on-disk persistence, and support for Lua scripting. 

Its popualr use cases include Gaming Leaderboards, Caching, Session Store, Rich Media Streaming, Geospatial, Machine Learning, Real-Time Analytics, Chat, Messaging, and Queues. 

## Redis Features <a name="features"></a>

The following are some of the most popular features offered by Redis:

### Redis Sentinel <a name="sentinel"></a>

The Redis Sentinel is a stand-alone distributed system that developers use to calibrate their instances and increase their availability to clients. 

It uses a series of monitoring processes, automatic failovers, and notifications to tell its users in case of faulty master and slave instances. 

It also reconfigures new connections automatically for applications whenever it's necessary. 

### Redis Cluster <a name="cluster></a>

This is a distributed form of Redis that automatically divides datasets among various nodes. 

It facilitates higher scalability and performance of database deployments, and ensures continuous operations even when node subsets cannot communicate with the other part of the cluster. 

### Redis Pub/Sub <a name="pub"></a>

Since you can use publish and subscribe (Pub/Sub) commands in Redis, you can create high-performance messaging services for your services and applications. 

You can also use the list data structures to execute atomic operations. 

### Redis Persistence <a name="persistence"></a>

Redis relies on a persistent disk storage to avoid network bottlenecks and survive process outages. 

Redis takes screenshots of data regularly and appends them with changes as they become available. 

You can then configure it to generate database backups at automatic intervals or on demand to ensure database integrity and durability. 

## Redis Commands <a name="commands"></a>

To run Redis commands on your computer, you should first install it. 

You can get the installation instructions for Redis on its official website by opening the following URL on your web browser:

https://redis.io/topics/quickstart

Although Redis is not native to Windows, Microsoft has made it sure that you can use Redis. 

You can download the .zip or .msi file from GitHub by opening the following URL on your web browser:

https://github.com/microsoftarchive/redis/releases

To start Redis, just run the following command from the terminal of your operating system:

```
redis-server
```

To check whether Redis is working, run the following command:

```
redis-cli 
```

This will open the Redis prompt as shown below:

![](Capture1.png)

The 127.0.0.1 is the IP address of your computer (localhost) while the 6379 is the port number on which the Redis server is running. 

Run the `ping` command:

![](Capture2.png)

The `PONG` output shows that Redis is successfully installed on your computer. 

### Setting a Key <a name="set"></a>
 
To set a Redis key, we use the `SET` command. 

For example:

```
SET sample_key "Hello World"
```
The above command helps us set a key named `sample_key`. 

If the comamnd runs successfully, it should return "OK".

![](Capture3.png)

### Getting a Key <a name="get"></a>

To get the value of a key, we use the `GET` command followed by the key name. 

For example:

```
GET sample_key
```

The command should return the value of the key named `sample_key` as shown below:

![](Capture4.png)

### Deleting a Key <a name="delete"></a>

To delete a Redis key, we use the `DEL` command followed by the name of the key. 

For example, let's delete the key named `sample_key`:

![](Capture5.png)

Since the key was deleted, the result is nil. 

### Setting Keys with Expiry <a name="expiry"></a>

You can set the expiry period of a key when creating it. 

This requires that you use the `SETEX` command. 

For example:

```
SETEX sample_key 50 "He said, Hello World!"
```

The key has been set with an expiry period of 50 seconds. 

If the command runs succerssfully, it will only return `OK`. 

To see the total time left for a key to expire, use the `TTL (Total Time Left)` command. 

For example:

```
TTL sample_key
```

The command runs as follows:

![](Capture6.png)

The output shows that only 47 seconds are left for the key to expire!
  
### Removing Key Timeout <a name="remove"></a>

To remove the expiry period from your Redis key, you should change it from being volatile to persistent. 

This means that the key won't expire. 

This is possible using the `PERSIST` command. 

For example:

```
PERSIST sample_key
```

The above command wil turn the key named `sample_key` from volatile to persistent. 

### Renaming a Key <a name="rename"></a>

To rename the curreny key, use the `RENAME` command. 

For example:

```
RENAME sample_key my_key
```

The above command will rename the key named `sample_key` to `my_key`. 

### Flushing Contents <a name="flush"></a>

To flush everything that you've saved so far, use the `FLUSHALL` command. 

For example:

![](Capture7.png)

The nil output shows that nothing is saved in Redis. 

## Conclusion: <a name="conclusion"></a>

This is what you've learnt in this article:

- Data stored in Cache can be accessed faster than data stored in disk. 

- Redis is a great tool for implementing Caching in applications. 

- Redis supports numerous data structures just like other programming languages. 

- Although Redis is not native to Windows, Microsoft has provided a way to use Redis in Windows. 
























