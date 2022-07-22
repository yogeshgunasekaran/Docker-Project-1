# Multistage Dockerfile

FROM openjdk:8 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone -b main https://github.com/yogeshgunasekaran/Docker-Project-1.git
RUN cd Docker-Project-1 && mvn install

FROM tomcat:8-jre11
LABEL "Project"="Project1"
LABEL "Author"="Yogesh"

RUN rm -rf /usr/local/tomcat/webapps/*

COPY --from=BUILD_IMAGE Docker-Project-1/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
