# jupyter_notebook/Dockerfile
FROM --platform=linux/amd64 jupyter/minimal-notebook

USER root

# Cài đặt các công cụ cần thiết
RUN apt-get update && \
    apt-get install -y gcc build-essential && \
    apt-get clean

# Copy requirements file và cài đặt Python dependencies
COPY ./requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt

# Cài đặt Java JDK
RUN apt-get update && \
    apt-get install -y openjdk-11-jdk && \
    apt-get clean;

# Set JAVA_HOME environment variable
ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64

# Quay lại user mặc định (non-root) để chạy Jupyter Notebook
USER $NB_UID

