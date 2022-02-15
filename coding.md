## QP1

NoSQL is a kind of database that doesn't have a fixed schema like a traditional RDBMS does. With the NoSQL databases the schema is defined by the developer at run time. They don't write normal SQL statements against the database, but instead use an API to get the data that they need. The NoSQL databases can usually scale across different physical servers easily without needing to know which server the data you are looking for is on.

However there are some trade offs for all this flexibility: The NoSQL databases are pretty feature lacking compared to the RDBMS systems like SQL Server, Oracle, DB2, MySQL, etc. There's no Service Broker, Transaction logging, ETL packages, etc.

---

Basically dispensing with the relational setup, with primary and foreign keys, and with the additional overhead involved in keeping transactional safety, often gives you extreme increases in performance. However this is not unique to the new databases/datastores, as eg MySQL has been tuned to perform at "NoSQL levels" by bypassing layers.

In short, you can often get impressive performance if you're ok with taking the risk of possibly losing data. Most NoSQL systems do this. Eg MongoDB stages data changes to be written when it's convenient. The data itself is safe and transactionally secure, but kept in volatile storage (memory). If you lose power you can't be 100% sure that you haven't lost data, or that you don't have corrupted data.

---

You'll find that NoSQL database have few common characteristics. They can be roughly divided into a few categories:

key/value stores
Bigtable inspired databases (based on the Google Bigtable paper)
Dynamo inspired databases
distributed databases
document databases

NoSQL databases may dispense with various portions of ACID in order to achieve certain other benefits--partition tolerance, performance, to distribute load, or to scale linearly with the addition of new hardware.

---

There are a lot of differences between the two of them. MongoDB is more like a traditional RDBMS (nobody shoot). CouchDB performs master-master replication. It's pretty well documented in this much ballyhooed blog post.

---

The reason why NoSQL has been so popular the last few years is mainly because, when a relational database grows out of one server, it is no longer that easy to use. In other words, they don't scale out very well in a distributed system. All of the big sites that you mentioned Google, Yahoo, Facebook and Amazon (I don't know much about Digg) have lots of data and store the data in distributed systems for several reasons. It could be that the data doesn't fit on one server, or there are requirements for high availability.

The properties of a distributed system can be described by the CAP Theorem. Of the three properties you can only have at most two:

C​onsistency
A​vailability
tolerance to network P​artitioning

Finally I would like to say that relational databases will remain popular. They are very flexible and maintainable. But they are not always the best choice.

---

You would use NoSQL for one main reason: scalability.

If your application needs to handle millions of queries per second, the only way to achieve it is to add more servers. That is very cheap and easy with NoSQL. In contrast, scaling a traditional SQL database is much more complicated.

---

Very fast writes and reads
Persistent data that won't get lost in a crash
Plays nice with PHP
Works well in the cloud (EC2)
High availability
Preferably open-source
The data needs to be able to be manipulated in a way to show statistics reports (sums, ranges, groupings, etc)