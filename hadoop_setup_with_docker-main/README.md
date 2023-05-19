# Hadoop setup with Docker Contaner

### Setup the Docker Environment 

> Pull the sequenceiq hadoop 
``` 
  docker pull sequenceiq/hadoop-docker:latest 
````

> Run the contaner with 3 ports 8088,50070,8042
```
  docker run -it -p 50070:50070 -p 8088:8088 -p 8042:8042 sequenceiq/hadoop-docker:latest /etc/bootstrap.sh -bash
```
> change to hadoop folder
```
  cd usr/local/hadoop/
```

> Create New input data file 
```
  vi input/data.txt
```
```
bin/hadoop fs -mkdir /input

bin/hadoop fs -put input/data.txt /input

bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.0.jar wordcount /input/data.txt /output
```
> List the output file
```
bin/hdfs dfs -cat /output/*
```
