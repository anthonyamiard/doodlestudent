FROM maven:3.8.4-jdk-11 AS build
WORKDIR /project
COPY . /project/
RUN mvn package -Dquarkus.package.type=uber-jar -Dmaven.test.skip=true

FROM openjdk:11
WORKDIR /backend
COPY --from=build /project/target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar /backend/
CMD [ "java", "-jar", "tlcdemoApp-1.0.0-SNAPSHOT-runner.jar" ]