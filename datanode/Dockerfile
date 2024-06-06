# datanode/Dockerfile
FROM hadoop-base

# Expose the datanode port
EXPOSE 9864

CMD ["bash", "-c", "service ssh start; $HADOOP_HOME/bin/hdfs datanode"]
