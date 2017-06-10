# assignment17.1

1. What is NoSQL data base?
Ans:
  A NoSQL database provides a mechanism for storage and retrieval of data which is modeled in means other than the tabular relations used in relational databases. 
2. How does data get stored in NoSQl database?

Ans:

There are 4 main NoSQL models:
Key-value stores, also known as hashmaps. Main representative: Cassandra.
Document store, which stores a big set of bytes under a key,  because documents are hierarchical, so you can have one document inside of another and so on. Main representative: Mongo DB.
Column oriented, stores columns only, the partitioning of data is simpler and based on the idea that you usually need just some columns, the columns can be stored on different computers, so the queries can be done all in parallel and therefore it is done much faster.
Graph databse. Graph stores are used to store information about networks of data, such as social connections. Graph stores include Neo4J and Giraph. Key-value stores are the simplest NoSQL databases. Every single item in the database is stored as an attribute name (or 'key'), together with its value

3. What is a column family in HBase?
 Ans:
A HBase table is comprised of one or more column families, each of which is stored in a separate set of regionfiles sharing a common key.A column family is a NoSQL object that contains columns of related data. It is a tuple (pair) that consists of a key-value pair, where the key is mapped to a value that is a set of columns

4. How many maximum number of columns can be added to HBase table?
 There is no store of column metadata outside of the internal KeyValue instances for a ColumnFamily. Thus, while HBase can support not only a wide number of columns per row, but a heterogeneous set of columns between rows as well, it is your responsibility to keep track of the column names.Default number is 1
5. Why columns are not defined at the time of table creation in HBase?

Ans:
   Column families must be declared up front at schema definition time whereas columns do not need to be defined at schema time but can be conjured on the fly while the table is up and running. 

6. How does data get managed in HBase?

Ans:
HBase supports several different compression algorithms which can be enabled on a ColumnFamily. Data block encoding attempts to limit duplication of information in keys, taking advantage of some of the fundamental designs and patterns of HBase, such as sorted row keys and the schema of a given table. Compressors reduce the size of large, opaque byte arrays in cells, and can significantly reduce the storage space needed to store uncompressed data.Compressors and data block encoding can be used together on the same ColumnFamily.
7. What happens internally when new data gets inserted into HBase table?

Ans:

Region boundaries have changed during the course of bulk load preparation, or between the preparation and completion steps, the completebulkload utility will automatically split the data files into pieces corresponding to the new boundaries. This process is not optimally efficient, so users should take care to minimize the delay between preparing a bulk load and importing it into the cluster, especially if other clients are simultaneously loading data through other means.
