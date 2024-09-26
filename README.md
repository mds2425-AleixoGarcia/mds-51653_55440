# Getting started with the Elastic Stack

 Looking for an Elastic Stack ("ELK" tutorial) that shows how to set up the Elastic Stack? In this tutorial, you learn how to get up and running quickly. First you install the core open source products:
 
[Elasticsearch](https://www.elastic.co/docs#install-elasticsearch)
[Kibana](https://www.elastic.co/docs#install-kibana)
[Beats](https://www.elastic.co/docs#install-beats)
[Logstach](https://www.elastic.co/docs#install-logstash)


Then you learn how to implement a system monitoring solution that uses Metricbeat to collect server metrics and ship the data to Elasticsearch, where you can search and visualize the data by using Kibana. After you get the basic setup working, you add Logstash for additional parsing.

To get started, you can install the Elastic Stack on a single VM or even on your laptop.

Implementing security is a critical step in setting up the Elastic Stack. To get up and running quickly with a sample installation, you skip those steps right now. Before sending sensitive data across the network, make sure you secure the [Elastic Stack](https://www.elastic.co/guide/en/elasticsearch/reference/6.6/elasticsearch-security.html) and enable [encrypted communications](https://www.elastic.co/guide/en/elasticsearch/reference/6.6/encrypting-communications.html).

## Before you login

   See the [Elastic Support Matrix](https://www.elastic.co/pt/support/matrix) for information about supported operating systems and product compatibility.
   Verify that your system meets the [minimum JVM requirements](https://www.elastic.co/guide/en/elasticsearch/reference/6.6/encrypting-communications.html) for Logstash and Elasticsearch.

## Install ElasticSearch

[Elasticsearch](https://www.elastic.co/pt/elasticsearch) is a real-time, distributed storage, search, and analytics engine. It can be used for many purposes, but one context where it excels is indexing streams of semi-structured data, such as logs or decoded network packets.

Elasticsearch can be run on your own hardware or using our hosted Elasticsearch Service on [Elastic Cloud](https://www.elastic.co/pt/cloud), which is available on AWS and GCP. You can [try out the Elasticsearch Service](https://www.elastic.co/pt/cloud/elasticsearch-service/signup) for free.

To download and install Elasticsearch, open a terminal window and use the commands that work with your system ([deb](https://www.elastic.co/docs#deb) for Debian/Ubuntu, [rpm](https://www.elastic.co/docs#rpm) for Redhat/Centos/Fedora, [mac](https://www.elastic.co/docs#mac) for OS X, and [win](https://www.elastic.co/docs#win) for Windows):

**deb**:
```
 curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.6.0.deb
sudo dpkg -i elasticsearch-6.6.0.deb
sudo /etc/init.d/elasticsearch start
```

**rpm**:
```
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.6.0.rpm
sudo rpm -i elasticsearch-6.6.0.rpm
sudo service elasticsearch start
```
**mac**:
 ```
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.6.0.tar.gz
tar -xzvf elasticsearch-6.6.0.tar.gz
cd elasticsearch-6.6.0
./bin/elasticsearch

```

**win**:

 1.Download the Elasticsearch 6.6.0 Windows zip file from the Elasticsearch download page.
 
 2.Extract the contents of the zip file to a directory on your computer, for example, C:\Program Files.
 
 3.Open a command prompt as an Administrator and navigate to the directory that contains the extracted files, for example:
 ```
 cd C:\Program Files\elasticsearch-6.6.0
```
Start Elasticsearch



   

   
 

 
 
