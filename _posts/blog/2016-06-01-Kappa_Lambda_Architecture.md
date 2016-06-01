---
layout: post
category: blog
title: "Kappa Architecture"
excerpt: "Kappa vs Lambda Architecture"
tags: [bigdata, hadoop, apache, hortonworks, cloudera,lambda,kappa,data lake]
comments: true
---

##### "How to beat the CAP theorem ?" - Lambda Architecture

Nathan Marz wrote a popular blog post describing an idea he called the [Lambda Architecture](http://nathanmarz.com/blog/how-to-beat-the-cap-theorem.html). The Lambda Architecture is an approach to building stream processing applications on top of MapReduce and Storm or similar systems which is widely accepted as of now.

##### How does it look like ? 

![Lambda Approach](/downloads/Lambda.png) ![Lambda Approach](/downloads/Neo2_1.png)

The Lambda Architecture is aimed at applications built around complex asynchronous transformations that need to run with low latency (a few seconds to a few hours). An immutable sequence of records is captured and fed into a batch system and a stream processing system in parallel and the transformation logic is implemented twice, once in the batch system and once in the stream processing system. Later we stitch together the results from both these systems at query time to produce the required answer.

We can swap in various similar systems for Kafka, Storm, and Hadoop, and also use two different databases to store the output tables, one optimized for real time and the other optimized for batch updates.A lot of variations are possible.

