hemn
====

Built on the concept in the book [Anathem](http://www.nealstephenson.com/anathem/) of [Hemn Space](http://anathem.wikia.com/wiki/Science) or [Configuration Space](http://en.wikipedia.org/wiki/Configuration_space) the goal of this project is to allow a conciousness to identify the systems around it and potentially dynamically determine how to communicate with the systems around it.  In this case a consciousness refers to an application, system or general observer which needs to determine the Hemn Space that is currently occupies.  If it needs to adjust to changes such as new services or changes in the services it should move into another Hemn space.

Terminology
----------

* Cosmi  - represents a group of similar systems commonly used in conjunction with each other.


Hemn Space Example
------------------

Assume you have the following set of systems that you want to organize based on solutions, functionality, and a general separation concerns.

* HBase Clusters
	* 2 Real Time Clusters
	* 2 Batch Clusters
* 3 Storm Clusters
* 6 (distinct) REST Endpoints for Applications

Due to performance reasons, distribution of workload or just separating a large client from overloading some of the smaller ones you might create two cosms like the following:

Cosmi 1
  * 1 Real Time HBase Cluster
  * 1 Batch HBase Cluster
  * 2 Storm Clusters
  * 3 REST Endpoints
Cosmi 2
  * 1 Real Time HBase Cluster
  * 1 Batch HBase Cluster
  * 1 Storm Clusters
  * 3 REST Endpoints

The goal should be that give the location of the Hemn Space information and the cosm name, the consciousness should be able to determine how to communicate with the systems inside of the cosmi.Additionally if a consciousness needs to move between cosms it could do so with no downtime.  This could be an example of moving a consuming consciousness to its own cosmi to reduce the burden on shared resources.


Implementation
-------------

The entire state of the Hemn Space will be stored and tracked using [Zookeeper](http://zookeeper.apache.org/).  Functionality provided inside of Zookeeper provides the ability to retrieve information, detect changes and easily determine providers and consumers of information in the Hemn Space.

Usage
-----

### Clients



#### Java/Scala



#### Ruby

Coming Eventually


