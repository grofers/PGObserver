FROM java:7-jre

RUN apt-get update -y && apt-get install -y postgresql-client ldap-utils maven openjdk-7-jdk git

RUN mkdir -p /app
WORKDIR /app
ADD . /app
RUN mvn clean package
RUN FILE_NAME=$(ls target/pgobserver-gatherer-*-jar-with-dependencies.jar | tail -1) && mv $FILE_NAME pgobserver-gatherer.jar
ADD pgobserver.yaml /root/.pgobserver.yaml

EXPOSE 8081

CMD ["java","-jar","/app/pgobserver-gatherer.jar"]
