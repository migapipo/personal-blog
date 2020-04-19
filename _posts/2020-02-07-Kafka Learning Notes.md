---
layout: post
title: Kafka Learning Notes


categories:
  - Technology
tags:
  - study

---
# Kafka Learning Notes

This is the learning notes about Kafka. I got to know Kafka from a meetup talk.I would like to record some interesting findings while I learning this new technology.
:blush: Let's start leanring! 

## Definition
Apache Kafka is an open-source stream-processing software platform developed by LinkedIn and donated to the Apache Software Foundation, written in Scala and Java. 
The project aims to provide a unified, high-throughput, low-latency platform for handling real-time data feeds.

Key concepts: 
- Kafka is run as a cluster on one or more servers that can span multiple datacenters.
- The Kafka cluster stores streams of records in categories called topics.
- Each record consists of a key, a value, and a timestamp.


## Capabilities

A streaming platform has three key capabilities:

- Publish and subscribe to streams of records, similar to a message queue or enterprise messaging system.
- Store streams of records in a fault-tolerant durable way.
- Process streams of records as they occur.

## Application

Kafka is generally used for two broad classes of applications:

Building real-time streaming data pipelines that reliably get data between systems or applications
Building real-time streaming applications that transform or react to the streams of data


## Reference
https://kafka.apache.org/intro
