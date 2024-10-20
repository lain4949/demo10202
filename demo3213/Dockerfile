FROM maven:3-eclipse-temurin-17 AS build
COPY . .
RUN cd /home/app && mvn clean package -Dmaven.test.skip=tru/
FROM eclipse-temurin:17-alpine
COPY --from=build /home/app/target/spring-practice-0.0.1-SNAPSHOT.jar /usr/local/lib/demo.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "demo.jar"]
