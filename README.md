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

 1.Download the Elasticsearch 6.6.0 Windows zip file from the [Elasticsearch download page](https://www.elastic.co/pt/downloads/elasticsearch).
 
 2.Extract the contents of the zip file to a directory on your computer, for example, ```C:\Program Files.```
 
 3.Open a command prompt as an Administrator and navigate to the directory that contains the extracted files, for example:
 ```
 cd C:\Program Files\elasticsearch-6.6.0
```
4.Start Elasticsearch

For other operating systems, go to the [Elasticsearch download page](https://www.elastic.co/pt/downloads/elasticsearch).

To learn more about installing, configuring, and running Elasticsearch, read [theElasticsearch Reference](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html).

## Make sure Elasticsearch is up and running

To test that the Elasticsearch daemon is up and running, try sending an HTTP GET request on port 9200.
 curl ```http://127.0.0.1:9200 ```
 
On Windows, if you don’t have cURL installed, point your browser to the URL.

You should see a response similar to this:
```
{
  "name" : "QtI5dUu",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "DMXhqzzjTGqEtDlkaMOzlA",
  "version" : {
    "number" : "6.6.0",
    "build_flavor" : "default",
    "build_type" : "tar",
    "build_hash" : "00d8bc1",
    "build_date" : "2018-06-06T16:48:02.249996Z",
    "build_snapshot" : false,
    "lucene_version" : "7.3.1",
    "minimum_wire_compatibility_version" : "5.6.0",
    "minimum_index_compatibility_version" : "5.0.0"
  },
  "tagline" : "You Know, for Search"
}
```

## Install Kibana

[kibana](https://www.elastic.co/pt/kibana) s an open source analytics and visualization platform designed to work with Elasticsearch. You use Kibana to search, view, and interact with data stored in Elasticsearch indices. You can easily perform advanced data analysis and visualize your data in a variety of charts, tables, and maps.

If you are running our hosted Elasticsearch Service on [Elastic Cloud](https://www.elastic.co/pt/cloud), then [Kibana can be enabled](https://www.elastic.co/guide/en/cloud/current/ec-enable-kibana.html) with the flick of a switch.

We recommend that you install Kibana on the same server as Elasticsearch, but it is not required. If you install the products on different servers, you’ll need to change the URL (IP:PORT) of the Elasticsearch server in the Kibana configuration file, ```kibana.yml```, before starting Kibana.

To download and install Kibana, open a terminal window and use the commands that work with your system:
 
**deb or rpm**:
```
curl -L -O https://artifacts.elastic.co/downloads/kibana/kibana-6.6.0-linux-x86_64.tar.gz
tar xzvf kibana-6.6.0-linux-x86_64.tar.gz
cd kibana-6.6.0-linux-x86_64/
./bin/kibana
```
**mac**:
```
curl -L -O https://artifacts.elastic.co/downloads/kibana/kibana-6.6.0-darwin-x86_64.tar.gz
tar xzvf kibana-6.6.0-darwin-x86_64.tar.gz
cd kibana-6.6.0-darwin-x86_64/
./bin/kibana
```
**win**:

 1. Download the Kibana 6.6.0 Windows zip file from the [kibana download]() page
 2. Extract the contents of the zip file to a directory on your computer, for example, ```C://Program Files```
 4. Start Kibana
 For other operating systems, go to the Kibana download page.

To learn more about installing, configuring, and running Kibana, read the Kibana Reference.

## Launch the Kibana web interface
 The Beats are open source data shippers that you install as agents on your servers to send operational data to Elasticsearch. Beats can send data directly to Elasticsearch or via Logstash, where you can further process and enhance the data.

Each Beat is a separately installable product. In this tutorial, you learn how to install and run Metricbeat with the system module enabled to collect system metrics.

To learn more about installing and configuring other Beats, see the Getting Started documentation:

 Colons can be used to align columns.

| Elastic Beats | To capture   :|
| ------------- |:-------------:|
| [AudiBeat]()  | Audit data   |
| col 2 is      | Log files    
| zebra stripes | Cloud data   :|
| HeartBeat     | Availiability monitoring |

