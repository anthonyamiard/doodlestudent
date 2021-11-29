FROM openjdk:11
COPY . /api
WORKDIR /api
RUN ./mvnw clean package -Dquarkus.package.type=uber-jar
CMD ["java", "-jar target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar"]