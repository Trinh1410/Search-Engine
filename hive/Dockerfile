# hive/Dockerfile
FROM hadoop-base

# Copy and extract Hive
COPY apache-hive-3.1.2-bin.tar.gz /tmp/
RUN tar -xzvf /tmp/apache-hive-3.1.2-bin.tar.gz -C /opt/ && \
    mv /opt/apache-hive-3.1.2-bin /opt/hive && \
    rm /tmp/apache-hive-3.1.2-bin.tar.gz

# Cài đặt JDBC driver cho MySQL
RUN curl -L -o /opt/hive/lib/mysql-connector-java-8.0.23.jar \
    https://repo1.maven.org/maven2/mysql/mysql-connector-java/8.0.23/mysql-connector-java-8.0.23.jar

ENV HIVE_HOME=/opt/hive
ENV PATH=$PATH:$HIVE_HOME/bin

# Copy hive-site.xml to Hive conf directory
COPY hive-site.xml $HIVE_HOME/conf/



