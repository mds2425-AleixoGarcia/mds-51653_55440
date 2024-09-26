# Getting started with the Elastic Stack

 Looking for an Elastic Stack ("ELK" tutorial) that shows how to set up the Elastic Stack? In this tutorial, you learn how to get up and running quickly. First you install the core open source products:
 
*Elasticsearch
*Kibana
*Beats
*Logstach


Then you learn how to implement a system monitoring solution that uses Metricbeat to collect server metrics and ship the data to Elasticsearch, where you can search and visualize the data by using Kibana. After you get the basic setup working, you add Logstash for additional parsing.

To get started, you can install the Elastic Stack on a single VM or even on your laptop.

Implementing security is a critical step in setting up the Elastic Stack. To get up and running quickly with a sample installation, you skip those steps right now. Before sending sensitive data across the network, make sure you secure the Elastic Stack and enable encrypted communications.

# Before you login

   See the Elastic Support Matrix for information about supported operating systems and product compatibility.
   Verify that your system meets the minimum JVM requirements for Logstash and Elasticsearch.

#Install ElasticSearch

Elasticsearch is a real-time, distributed storage, search, and analytics engine. It can be used for many purposes, but one context where it excels is indexing streams of semi-structured data, such as logs or decoded network packets.

Elasticsearch can be run on your own hardware or using our hosted Elasticsearch Service on Elastic Cloud, which is available on AWS and GCP. You can try out the Elasticsearch Service for free.

To download and install Elasticsearch, open a terminal window and use the commands that work with your system (deb for Debian/Ubuntu, rpm for Redhat/Centos/Fedora, mac for OS X, and win for Windows):
