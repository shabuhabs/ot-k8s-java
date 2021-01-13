FROM openjdk:8-jre
ADD target/stock-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8030

COPY signalfx-tracing.jar .

#ENTRYPOINT ["java","-jar","/app.jar"]

ENTRYPOINT ["java","-javaagent:./signalfx-tracing.jar", "-Dsignalfx.service.name=stock" ,"-jar","/app.jar"]
