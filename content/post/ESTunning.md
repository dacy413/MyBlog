+++
categories = ["ES"]
date = "2016-02-05T08:15:42+08:00"
description = "ES tunning plane"
keywords = ["ES"]
title = "ES Tunning"

+++


我们现在的ES是1.4

看了一些资料 比如设置启用Doc Values 将field data cache序列化成文件降低对查询结果进行倒排会使用大量的cache

大量数据我们的确可以考虑使用scan & scroll api 之类的

Shards

index分页为几部分进行分布式多节点或者单节点部署

Replicas

1 容错 2 查询时进行负载均衡
