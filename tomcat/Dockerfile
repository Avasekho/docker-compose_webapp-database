FROM tomcat:9.0.19-jre8-alpine
WORKDIR /usr/local/tomcat/webapps/
RUN ln -s /usr/local/tomcat/webapps/App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT /usr/local/tomcat/webapps/hwk12
WORKDIR /tmp/
RUN echo 'app42.paas.db.username = "webappuser"' >> "Config.properties"
RUN echo 'app42.paas.db.port = "5432"' >> "Config.properties"
RUN echo 'app42.paas.db.password = "dbpassword"' >> "Config.properties"
RUN echo 'app42.paas.db.ip = "db"' >> "Config.properties"
RUN echo 'app42.paas.db.name = "webappdb"' >> "Config.properties"
RUN mv "Config.properties" /usr/local/tomcat/webapps/ROOT/