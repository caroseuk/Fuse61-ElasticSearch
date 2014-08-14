Fuse61-ElasticSearch Example
============================

An example of using JBoss Fuse ESB, JBoss Fuse MQ and Fabric to build highly scalable messaging solutions (with analytics).

This example will build and install an Camel/ActiveMQ/ElasticSearch solution and install it in your local Maven repository.

After running the installed Karaf script, multiple containers will be created containing A message producer, broker and multiple consumers. As well as this, 3 metrics child containers (**metrics1, metrics2, metrics3**) will be created with the **insight-core** profile installed. The insight-kibana profile will also be added to the root container to enable the web based ElasticSearch and Kibana3 console.

<h4>Getting started...</h4>

1. Clone this repo  
2. navigate to the **fuse-fabric-mq-example** root folder and execute the following command:  
`$ mvn clean install`  
4. Launch JBoss Fuse 6.1 ESB  
5. Run the installed Karaf installer using the following command within the console:  
`shell:source mvn:org.fusebyexample.mq/fuse-fabric-mq-example-features/0.0.1-SNAPSHOT/karaf/installer`  
6. Wait for containers to successfully provision as successful  
7. Use hawtio to see what's going on!
8. To see the URL's to access ElasticSearch/Kibana3/ you can run the following command:
`cluster-list`  

**Hawtio** - http://localhost:8181/hawtio
**ElasticSearch** - http://localhost:8181/eshead
**Kibana** - http://localhost:8181/kibana3  

<h4>What you should see</h4>
You should be able to see the following areas:

<h5>Camel/AMQ Producer/Consumers</h5>
A Camel based producer is generating messages every second into the AMQ broker, two consumers are consuming the messages from the AMQ broker.

<h5>ElasticSearch User Interface/Console</h5>
After pointing you browser at the ElasticSearch web interface, you will be presented with the status page of the cluster. from here you can browse around the interface and navigate through the multiple tabs.

<h5>Kibana3 Graph/Charts</h5>
After pointing your browser at the Kibana3 URL, you will be able to create graphs and charts based on the metrics found within ElasticSearch.

<h4>Want to see what else you can do?</h4>

2. Add the **insight-camel** profile to the child containers containing any camel routes to collect data on exchanges made. These can then be filtered from within the ElasticSearch web console.

# Useful links

* [Jboss Fuse](https://access.redhat.com/site/documentation/JBoss_Fuse/)
* [hawtio](http://hawt.io/)
* [Fabric](http://fabric8.io)
* [Competing Consumer EIP](http://www.enterpriseintegrationpatterns.com/CompetingConsumers.html)

