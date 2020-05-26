# bigdata-groupD-hue

## Team members

- Maha Lakshmi Kongari
- Venkat Prudhvi Dommaraju
- Dheeraj Edupuganti
- Sumanth Gorantla

![](groupd.PNG)

## GitHub Profile Links

- Maha Lakshmi Kongari - [https://github.com/MAHALAKSHMIKONGARI](https://github.com/MAHALAKSHMIKONGARI)

- Venkat Prudhvi Profile link - [https://github.com/prudhvi15](https://github.com/prudhvi15)

- Dheeraj Edupuganti GitHub profile link - [https://github.com/Dheeraj0327](https://github.com/Dheeraj0327)

- Sumanth Gorantla GitHub profile link - [https://github.com/gorantla96](https://github.com/gorantla96)

## Apache Solr:
Description: 

Solr is an open-source enterprise-search platform, written in Java, from the Apache Lucene project. Its major features include full-text search, hit highlighting, faceted search, real-time indexing, dynamic clustering, database integration, NoSQL features and rich document handling. 

## Installing Solr on local machine:
1. Install the binary from the below link,
http://apache.mirrors.hoobly.com/lucene/solr/8.5.1/solr-8.5.1.tgz

1. Extract the Solr tar file using the command,
```tar zxf solr-8.5.1.tgz```
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/tar%20in%20shell.png?raw=true)

1. Redirect the Solr folder created to C:\
Set up the environment variable, SOLR_HOME = C:\solr-8.5.1 and add %SOLR_HOME%\bin in path.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/env.png?raw=true)
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/envi.png?raw=true)

1. Open powershell from C:\solr-8.5.1\bin and run the following commands:

```./solr start -p 8080``` - To start the solr in the port 8080.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/start.png?raw=true)
 ```./solr status``` - To check the status of solr node.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/status.png?raw=true)
5. Open the browser and run solr(use localhost:8080 to open console).
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/localhost.png?raw=true)

## Creating and Deleting core using command
1. To create core use command ```solr create -c core name```.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/create.png?raw=true)

1. To delete core use command ```solr delete -c core name```.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/delete.png?raw=true)

## Creating and Deleting core using console
1. To create a new core navigate to Core Admin in solr console and then click Add Core. It requires data folder and config files.
For this, we have to create the folder with the core name and then, in C:\solr-8.5.1\corename folder, create two folders named conf and data. Include the default files of config from server>solr>configsets>default. Then, go to the solr console and click add core with the appropriate data and config files. we can observe that the core has been created.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Ccreate.png?raw=true)

1. To delete the code from solr console, just navigate to core admin and select the core that we want to delete and click on unload.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Cdelete.png?raw=true)


## Indexing data through solr
1. After creating a core, select the particular core in the console and navigate to Query. Then select response format as json and click on execute query.
1. The result shows that number of files are zero as this is the newely created core and data is not yet indexed. In order to index the data we will use sample data.
![](console.png)
1. Open powershell from C:\solr-8.5.1\example\exampledocs and run ```java -Dc=core name -jar post.jar *.xml``` command. Now we can observe data is indexed into the desired core.
![](indexing.png)
1. Now go to solr console and select core from options and navigate to query. Then select response format as json and click on execute query.
1. We can also use filters such as filter query(fq), field list(fl) to get sorted data.

![](solr_console.png)

## APACHE HIVE 

The Apache Hive data warehouse software facilitates reading, writing, and managing large datasets residing in distributed storage using SQL. Structure can be projected onto data already in storage. 

A command line tool and JDBC driver are provided to connect users to Hive.






References:
- [https://www.youtube.com/watch?v=b45sSrHC_p8](https://www.youtube.com/watch?v=b45sSrHC_p8)
- [https://www.youtube.com/watch?v=rxoS1p1TaFY&t=25s](https://www.youtube.com/watch?v=rxoS1p1TaFY&t=25s)


