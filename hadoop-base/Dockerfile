# hadoop-base/Dockerfile
FROM openjdk:8-jdk

# Install necessary packages
RUN apt-get update && \
    apt-get install -y ssh pdsh rsync curl

# Setup Hadoop environment variables
ENV HADOOP_VERSION=3.2.2
ENV HADOOP_HOME=/opt/hadoop
ENV HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop
ENV PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin

# Copy and extract Hadoop
COPY hadoop-$HADOOP_VERSION.tar.gz /tmp/
RUN tar -xzvf /tmp/hadoop-$HADOOP_VERSION.tar.gz -C /opt/ && \
    mv /opt/hadoop-$HADOOP_VERSION $HADOOP_HOME && \
    rm /tmp/hadoop-$HADOOP_VERSION.tar.gz

# Setup SSH
RUN ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa && \
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys && \
    chmod 0600 ~/.ssh/authorized_keys

COPY config/* $HADOOP_CONF_DIR/

# Expose ports
EXPOSE 9870 8088 9000 10020 19888 8042 22

CMD ["bash", "-c", "service ssh start; bash"]

