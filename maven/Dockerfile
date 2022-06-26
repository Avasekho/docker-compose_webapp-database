FROM maven:3.8.5-jdk-11
RUN mkdir /artifact_folder/
COPY "App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war" "/artifact_folder/App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war"
WORKDIR /tmp/
RUN mkdir /tomcat_root/
RUN echo 'app42.paas.db.username = "webappuser"' >> "Config.properties"
RUN echo 'app42.paas.db.port = "3306"' >> "Config.properties"
RUN echo 'app42.paas.db.password = "dbpassword"' >> "Config.properties"
RUN echo 'app42.paas.db.ip = "db"' >> "Config.properties"
RUN echo 'app42.paas.db.name = "webappdb"' >> "Config.properties"
RUN mv "Config.properties" /tomcat_root/