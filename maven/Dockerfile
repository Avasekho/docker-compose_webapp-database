FROM maven:3.8.5-jdk-11
ARG DBUSERNAME
ARG DBPORT
ARG DBPASSWORD
ARG DBIP
ARG DBNAME
WORKDIR /tmp/
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/
RUN echo "app42.paas.db.username = ${DBUSERNAME}" >> "Config.properties" \
&& echo "app42.paas.db.port = ${DBPORT}" >> "Config.properties" \
&& echo "app42.paas.db.password = ${DBPASSWORD}" >> "Config.properties" \
&& echo "app42.paas.db.ip = ${DBIP}" >> "Config.properties" \
&& echo "app42.paas.db.name = ${DBNAME}" >> "Config.properties" \
&& mv -f "Config.properties" /tmp/App42PaaS-Java-MySQL-Sample/WebContent/
RUN mvn clean package
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/target/
RUN mkdir /artifact_folder/
RUN mv -f "App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war" /artifact_folder/