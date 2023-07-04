FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install
FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=build /app/target/zuul-0.0.1-SNAPSHOT.jar /app
EXPOSE 9999
CMD ["java", "-jar", "zuul-0.0.1-SNAPSHOT.jar"]



# Stage 1: Build the application
# FROM maven:3.8.1-openjdk-11-slim AS build
# WORKDIR /app
# COPY pom.xml .
# RUN mvn dependency:go-offline

# COPY src ./src
# RUN mvn package -DskipTests

# # Stage 2: Create a minimal image with only the JAR file
# FROM openjdk:11-jre-slim
# WORKDIR /app
# COPY --from=build /app/target/my-springboot-app.jar ./my-springboot-app.jar

# # Expose the port that your application listens on
# EXPOSE 8080

# # Set the entry point and command to run the application
# ENTRYPOINT ["java", "-jar", "my-springboot-app.jar"]