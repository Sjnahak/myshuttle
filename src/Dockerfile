FROM tomcat:9-jre8-alpine

RUN apk --update add curl ca-certificates tar 
RUN set -x \
    && mkdir /home/mysql \
    && curl -fSL https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-8.0.26.tar.gz -o /home/mysql/mysql-connector.jar \
    && cd /home/mysql \
    && tar -xzvf mysql-connector.jar \
    && pwd \
    && mkdir -p /usr/share/java \
    && mv /home/mysql/mysql-connector-java-8.0.26/mysql-connector-java-8.0.26.jar /usr/share/java/mysql-connector-java.jar \
    && cd /home \
    && rm -R *

RUN export CLASSPATH=$CLASSPATH:/usr/share/java/mysql-connector-java.jar

ADD myshuttledev.war /usr/local/tomcat/webapps/myshuttledev.war

