# nodemanager/Dockerfile
FROM hadoop-base

# Expose the NodeManager port
EXPOSE 8042

CMD ["bash", "-c", "service ssh start; $HADOOP_HOME/bin/yarn nodemanager"]
