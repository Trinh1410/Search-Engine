# hbase/Dockerfile
FROM hadoop-base

# Copy and extract HBase
COPY hbase-2.4.8-bin.tar.gz /tmp/
RUN tar -xzvf /tmp/hbase-2.4.8-bin.tar.gz -C /opt/ && \
    mv /opt/hbase-2.4.8 /opt/hbase && \
    rm /tmp/hbase-2.4.8-bin.tar.gz

ENV HBASE_HOME=/opt/hbase
ENV PATH=$PATH:$HBASE_HOME/bin

# Copy hbase-site.xml to HBase conf directory
COPY hbase-site.xml $HBASE_HOME/conf/

# Khởi động dịch vụ Thrift khi container khởi động
CMD ["bash", "-c", "start-hbase.sh; hbase thrift start -p 9090 --infoport 9095"]

