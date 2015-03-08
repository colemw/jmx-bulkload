Using JmxCassandraBulkLoader

To execute the jar, move all sstable files from the snapshots folder into a directory with a naming convention of 
/keyspace_name/column_family_name/

The following set of files is an example of the contents of a snapshots folder taken as a backup:

-rw-r--r--  1 cassandra cassandra     1500 Apr 18 21:13 Keyspace1-Standard1-jb-1-CRC.db
-rw-r--r--  1 cassandra cassandra 24505422 Apr 18 21:13 Keyspace1-Standard1-jb-1-Data.db
-rw-r--r--  1 cassandra cassandra       74 Apr 18 21:13 Keyspace1-Standard1-jb-1-Digest.sha1
-rw-r--r--  1 cassandra cassandra   110736 Apr 18 21:13 Keyspace1-Standard1-jb-1-Filter.db
-rw-r--r--  1 cassandra cassandra  1851129 Apr 18 21:13 Keyspace1-Standard1-jb-1-Index.db
-rw-r--r--  1 cassandra cassandra     4389 Apr 18 21:13 Keyspace1-Standard1-jb-1-Statistics.db
-rw-r--r--  1 cassandra cassandra    13181 Apr 18 21:13 Keyspace1-Standard1-jb-1-Summary.db
-rw-r--r--  1 cassandra cassandra       79 Apr 18 21:13 Keyspace1-Standard1-jb-1-TOC.txt

The schema for the keyspace and column familiy must be recreated before starting the JmxCassandraBulkLoader

To execute the application, issue the following command by replacing the data path and host:port to the correct arguments:

(jmx port should stay 7199 unless overridden with a different value in the cassandra yaml file)

java -jar JmxCassandraBulkLoader.jar /data/cassnadra/tmp/Keyspace1/Standard1 dev-use1d-pr-34-mjd-cadb-0001.prv-openclass.com:7199
