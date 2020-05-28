# bigdata-groupD-hue

# Apache Solr and Apache Hive

## Team members

- Maha Lakshmi Kongari
- Venkat Prudhvi Dommaraju
- Dheeraj Edupuganti
- Sumanth Gorantla

![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/groupd.PNG)

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
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/tar%20in%20shell.png)

1. Redirect the Solr folder created to C:\
Set up the environment variable, SOLR_HOME = C:\solr-8.5.1 and add %SOLR_HOME%\bin in path.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/env.png)
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/envi.png)

1. Open powershell from C:\solr-8.5.1\bin and run the following commands:

```./solr start -p 8080``` - To start the solr in the port 8080.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/start.png)
 ```./solr status``` - To check the status of solr node.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/status.png)
5. Open the browser and run solr(use localhost:8080 to open console).
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/localhost.png)

## Creating and Deleting core using command
1. To create core use command ```solr create -c core name```.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/create.png)

1. To delete core use command ```solr delete -c core name```.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/delete.png)

## Creating and Deleting core using console
1. To create a new core navigate to Core Admin in solr console and then click Add Core. It requires data folder and config files.
For this, we have to create the folder with the core name and then, in C:\solr-8.5.1\corename folder, create two folders named conf and data. Include the default files of config from server>solr>configsets>default. Then, go to the solr console and click add core with the appropriate data and config files. we can observe that the core has been created.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/Ccreate.png)

1. To delete the code from solr console, just navigate to core admin and select the core that we want to delete and click on unload.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/Cdelete.png)


## Indexing data through solr
1. After creating a core, select the particular core in the console and navigate to Query. Then select response format as json and click on execute query.
1. The result shows that number of files are zero as this is the newely created core and data is not yet indexed. In order to index the data we will use sample data.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/console.png)
1. Open powershell from C:\solr-8.5.1\example\exampledocs and run ```java -Dc=core name -jar post.jar *.xml``` command. Now we can observe data is indexed into the desired core.
![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/indexing.png)
1. Now go to solr console and select core from options and navigate to query. Then select response format as json and click on execute query.
1. We can also use filters such as filter query(fq), field list(fl) to get sorted data.

![](https://github.com/MAHALAKSHMIKONGARI/bigdata-groupD-hue/blob/master/Images/solr_console.png)

# Apache Hive

## Description

- Hive is a datawarehouse software project built on top of hadoop for providing data query and analysis. Hive supports analysis of large datasets stored in HDFS and compatable file systems.

- It provides a SQL-like query language called HiveQL with schema on read and transparently converts queries to MapReduce, Apache Tez and Spark jobs.

## Creating a table in hive

- Let us consider the table orders which contains the details of the order such as the customername, Orderid,country,city and zipcode.

- ```create table orders (Customername String comment "Name of the cutomer", orderid int,``` 

  ```country String comment "Country from where the item is ordered", city String, ```

  ```Zipcode BigInt comment "Zipcode/postal code of the location where the item is to be delivered") ```

  ```row format delimited fields terminated by ',' lines terminated by '\n' stored as textfile;```.

- Comment is used to understand about the particular column.

## Inserting values into table

- ```insert into table orders values('Dheeraj',1234,'zambia','Ndola',50100), ```

  ```('Sumanth',1957,'India','Guntur',522007),```

  ```('Prudhvi',3453,'USA','Maryville',64468),```

  ```('Maha',4589,'Germany','Berlin',453289);```.


## Altering table in HIVE

- The query used to change name of the table ```ALTER TABLE orders RENAME TO order;```.

- The query used to drop a column is ``` ALTER TABLE order REPLACE COLUMNS
  (customername string, orderid int, country String, zipcode BigInt)```.

- The above query will drop a column named as city.
- The query used to change the column name is ```ALTER TABLE order CHANGE city Location String;```.

- The query used to add columns in a table is ```ALTER TABLE order ADD COLUMNS ( 
  cname String COMMENT 'name of the customer');```.

## Dropping tables in HIVE

- The query used to drop table from a database is ```drop table IF EXISTS order;```.

## Queries used

- Query used to display the table where customer name starts with "a"
 
  ``` SELECT * FROM order```
 
  ```WHERE customername LIKE 'a%'; ```
 
- Query used to count the number of orders 
  ```SELECT Count(orderid) FROM orders;```
  
 - This query returns the customername and country from the  orders table. Where zipcode is 64668 and displays them.
 
   ```SELECT orders.customername, order.country FROM orders ```
  
   ```WHERE zipcode = 64468;```
  
 -  Query used to display the table where city name starts with M and end with E
  
    ```SELECT * FROM order```
   
    ```WHERE countryname LIKE 'm%e';```
   
 - Query used to display the table where order number ranges between 1 to 10
   
   ```SELECT * FROM order```

   ```WHERE orderid BETWEEN 1 AND 10;```
  
  
### References:
- [https://www.youtube.com/watch?v=b45sSrHC_p8](https://www.youtube.com/watch?v=b45sSrHC_p8)
- [https://www.youtube.com/watch?v=rxoS1p1TaFY&t=25s](https://www.youtube.com/watch?v=rxoS1p1TaFY&t=25s)
- [https://en.wikipedia.org/wiki/Apache_Hive](https://en.wikipedia.org/wiki/Apache_Hive)
- [https://www.tutorialspoint.com/hive/index.htm](https://www.tutorialspoint.com/hive/index.htm)
