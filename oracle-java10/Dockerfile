#
# Oracle Java 9 Dockerfile
#
# https://github.com/cogniteev/docker-oracle-java
# https://github.com/cogniteev/docker-oracle-java/tree/master/oracle-java9
#

# Pull base image.
FROM ubuntu:16.04

ARG version=10.0.1-1~linuxuprising+1

# Install Java.
RUN \
  apt-get update && \
  apt-get install -y software-properties-common && \
  echo oracle-java10-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  add-apt-repository -y ppa:linuxuprising/java && \
  apt-get update && \
  apt-get install -y oracle-java10-installer=${version} && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk10-installer


# Define working directory.
WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-10-oracle

# Define default command.
CMD ["bash"]
