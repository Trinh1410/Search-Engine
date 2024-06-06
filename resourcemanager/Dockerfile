# resourcemanager/Dockerfile
FROM hadoop-base

# Expose the ResourceManager port
EXPOSE 8088

CMD ["bash", "-c", "service ssh start; $HADOOP_HOME/bin/yarn resourcemanager"]
