FROM maven:3.8.5-jdk-11
ARG DBUSERNAME
ARG DBPORT
ARG DBPASSWORD
ARG DBIP
ARG DBNAME
WORKDIR /tmp/
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/
RUN mvn clean package
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/target/
RUN mkdir /artifact_folder/
RUN mv -f "App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war" /artifact_folder/
COPY ../Config.properties /artifact_folder/App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT/