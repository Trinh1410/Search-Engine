# namenode/Dockerfile
FROM hadoop-base

# Expose the namenode ports
EXPOSE 9870 9000

# Format the HDFS namenode
RUN $HADOOP_HOME/bin/hdfs namenode -format

CMD ["bash", "-c", "service ssh start; $HADOOP_HOME/bin/hdfs namenode"]
