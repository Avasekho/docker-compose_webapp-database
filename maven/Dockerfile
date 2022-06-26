FROM maven:3.8.5-jdk-11
WORKDIR /tmp/
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/
RUN mvn clean install
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/target/
RUN mkdir /artifact_folder/
RUN mv "App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war" /artifact_folder/
WORKDIR /tmp/
RUN mkdir /tomcat_root/
RUN echo 'app42.paas.db.username = "webappuser"' >> "Config.properties"
RUN echo 'app42.paas.db.port = "3306"' >> "Config.properties"
RUN echo 'app42.paas.db.password = "dbpassword"' >> "Config.properties"
RUN echo 'app42.paas.db.ip = "84.201.166.180"' >> "Config.properties"
RUN echo 'app42.paas.db.name = "webappdb"' >> "Config.properties"
RUN mv "Config.properties" /tomcat_root/