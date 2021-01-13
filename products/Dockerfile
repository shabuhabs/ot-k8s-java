FROM openjdk:8-jre
ADD target/products-0.0.1-SNAPSHOT.jar app.jar
ADD products.yml app-config.yml
EXPOSE 8020

COPY signalfx-tracing.jar .

ENTRYPOINT ["java","-javaagent:signalfx-tracing.jar", "-Dsignalfx.service.name=products", "-jar","app.jar", "server", "app-config.yml"]

