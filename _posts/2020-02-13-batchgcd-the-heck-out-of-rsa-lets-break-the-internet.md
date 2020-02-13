---
layout: post
title: BatchGCD the heck out of RSA! Lets break the Internet
description: A small introduction to BatchGCD and RSA keys
categories:
  - Cryptographie
  - Hacking
image: /assets/images/blackboard-mathematics.jpg
author: stan_girard
---
# SSLCertificates

The first step is to gather millions of SSL certificates. I found two solutions that i can share, you either download it from a website or you

Download [Top10MillionWebsites](https://www.domcop.com/files/top/top10milliondomains.csv.zip) or Crawl the data from [CommonCrawl](https://commoncrawl.org/the-data/get-started/) which is 60TB of Crawled Websites. With a powerfull enough computer you could parse websites name and get millions of websites.

## Get Millions of domains in seconds
---


We are going to query the [Common Crawl](https://commoncrawl.org/) S3 bucket to get the list of all the domains it has crawled


### AWS Athena
---

[Amazon Athena](https://aws.amazon.com/athena/) is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.

Athena is easy to use. Simply point to your data in Amazon S3, define the schema, and start querying using standard SQL. Most results are delivered within seconds. With Athena, there’s no need for complex ETL jobs to prepare your data for analysis. This makes it easy for anyone with SQL skills to quickly analyze large-scale datasets.



---
 Open the [Athena query editor](https://console.aws.amazon.com/athena/home?region=us-east-1#query).

---
 Select us-east-1 as your location

---
Run the query 
```SQL
CREATE DATABASE ccindex
```
This will create a database

---
Create a new table with the following query 
```SQL
CREATE EXTERNAL TABLE IF NOT EXISTS ccindex (
  url_surtkey                   STRING,
  url                           STRING,
  url_host_name                 STRING,
  url_host_tld                  STRING,
  url_host_2nd_last_part        STRING,
  url_host_3rd_last_part        STRING,
  url_host_4th_last_part        STRING,
  url_host_5th_last_part        STRING,
  url_host_registry_suffix      STRING,
  url_host_registered_domain    STRING,
  url_host_private_suffix       STRING,
  url_host_private_domain       STRING,
  url_protocol                  STRING,
  url_port                      INT,
  url_path                      STRING,
  url_query                     STRING,
  fetch_time                    TIMESTAMP,
  fetch_status                  SMALLINT,
  content_digest                STRING,
  content_mime_type             STRING,
  content_mime_detected         STRING,
  content_charset               STRING,
  content_languages             STRING,
  warc_filename                 STRING,
  warc_record_offset            INT,
  warc_record_length            INT,
  warc_segment                  STRING)
PARTITIONED BY (
  crawl                         STRING,
  subset                        STRING)
STORED AS parquet
LOCATION 's3://commoncrawl/cc-index/table/cc-main/warc/';
```

This will map the table ccindex that your created woth the location of the S3 bucket where the data is store

---
Run 
```SQL 
MSCK REPAIR TABLE ccindex
```

Note that you need to rerun this command every month as new data is added by the commo crawl foundation.

---
Run
```SQL
SELECT DISTINCT(url_host_name)
FROM "ccindex"."ccindex"
WHERE crawl = 'CC-MAIN-2018-05'
  AND subset = 'warc'
  AND url_host_tld = 'no'
```

This will return all the hostname from Norway that were crawled in May 2018

![](images/AWS-ATHENA-NORWAY-EXAMPLE.png
)

```SQL
SELECT COUNT(*) AS count,
       url_host_registered_domain
FROM "ccindex"."ccindex"
WHERE crawl = 'CC-MAIN-2018-05'
  AND subset = 'warc'
  AND url_host_tld = 'no'
GROUP BY  url_host_registered_domain
HAVING (COUNT(*) >= 100)
ORDER BY  count DESC
```
This Query will return all the url_host_registered_domain count from Norway

**Mother of all queries** -> How to get 27M domains in 30seconds:

```SQL
SELECT DISTINCT(url_host_name)
FROM "ccindex"."ccindex"
WHERE subset = 'warc'
```

## Get the certificates

### Javascript Hell
Requesting millions of certificates isn't an easy task. As a javascript developper I never encountered such a task. It needs to be fast and efficient. I got to experience my first memory leak in Nodejs, out of memory. I also experienced low request per second (40 per seconds).

You can check index.js in the trashCode folder if you want to see the implementation on JS.

### Let's Go Python 

I decided to move to python3 to avoid many of the headaches that I got with Nodejs. The results were not as expected (60-70) per seconds. No memory issues this time !

You can check test.py if you want to see the implementation in Python.

### Go for the win

Python was not good enough, Goland seemed like a good fit. Never used before but seemed like a good choice.

The program can be found in src/main.go

```bash
cat domainnames | go run main.go
```

You need to have one domain per line
#### V2 of main.go

> The V2 of main.go allows you to skip the next steps.

## Process the certificates

We need to decode and parse the certificates to find the information that we need. In my case the issuer, n and e

### Javascript Hell Again

I might not have learned the lesson the first time but i tried again with JS. This time I had to read 4.5M files. 

You can find my programs in filewalker.js, read.js and readfile.js

### Python for the win

I then decided to move on and use python.
The script decodes the certificates files from a folder and insert the corresponding values in a database.

## Batch GCD 

Now it is time to hack !

I created a python notebook MultiplyCerts to see the basic implementation and complexity of a Batch GCD implementation.

I found out that the complexity of the basic implementation of Batch GCD is X^2

You can find the results in MultiplyCerts.htlm

### Batch GCD Implementation

It can then be used (for example) by a project like (batch-GCD)[https://github.com/zugzwang/batchgcd] which implement the algo from (here)[https://facthacks.cr.yp.to/batchgcd.html] developed by DJ Bernstein to find weak primes.

(C++)+GMP implementation of the Batch GCD algorithm, by Daniel Bernstein. This algorithm, described in How To Find Smooth Parts Of Integers, allows to compute pairwise GCDs of a list of integers in quasilinear time and memory. See e.g. factorable.net, which also provides source code.








