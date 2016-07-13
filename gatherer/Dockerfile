FROM java:7-jre

RUN apt-get update -y && apt-get install -y postgresql-client ldap-utils maven openjdk-7-jdk git

RUN mkdir -p /app
WORKDIR /app
ADD . /app
RUN mvn clean package
ADD pgobserver.yaml /root/.pgobserver.yaml

EXPOSE 8081

CMD ["java","-jar","/app/target/pgobserver-gatherer.jar"]
