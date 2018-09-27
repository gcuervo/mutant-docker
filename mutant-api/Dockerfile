FROM maven:3.5-jdk-8 as build
WORKDIR /app
COPY . /app
RUN mvn install

FROM openjdk:8
WORKDIR /app
COPY --from=build app/target/mutant.jar /app
EXPOSE 8090
ENTRYPOINT ["java","-jar","mutant.jar"]
