FROM maven:3.8.5-jdk-11
WORKDIR /tmp/
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/
RUN echo "app42.paas.db.username = webappuser" >> "Config.properties" \
&& echo "app42.paas.db.port = 3306" >> "Config.properties" \
&& echo "app42.paas.db.password = dbpassword" >> "Config.properties" \
&& echo "app42.paas.db.ip = db" >> "Config.properties" \
&& echo "app42.paas.db.name = webappdb" >> "Config.properties" \
&& mv -f "Config.properties" /tmp/App42PaaS-Java-MySQL-Sample/WebContent/
RUN mvn package
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample/target/
RUN mkdir /artifact_folder/
RUN mv -f "App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war" /artifact_folder/