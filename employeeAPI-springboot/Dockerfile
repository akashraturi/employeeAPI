FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install
FROM openjdk:11
RUN mkdir /employee
COPY --from=builder /app/target/*.jar  /employee
WORKDIR /employee
CMD ["java","-jar","employee-1.0.jar"]
