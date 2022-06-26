FROM maven:3.8.5-jdk-11
WORKDIR /tmp/
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/
RUN mvn clean install
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/target/
RUN mkdir /artifact_folder/
RUN mv "App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war" /artifact_folder/