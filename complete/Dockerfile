# Build Stage : Java Spring Boot APP
FROM maven:3.9.6-eclipse-temurin-21 AS builder
WORKDIR     /app
COPY pom.xml   .
COPY src   ./src

# Build the application
RUN mvn clean package -DskipTests


# Runtime Stage:

FROM eclipse-temurin:17-jre-jammy
#FROM gcr.io/distroless/java21:nonroot
WORKDIR     /app
COPY --from=builder /app/target/*.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]

