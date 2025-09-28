# ビルド用ステージ
FROM eclipse-temurin:21-jdk AS build

WORKDIR /app

COPY gradlew build.gradle settings.gradle /app/
COPY gradle /app/gradle
RUN ./gradlew --version

COPY . /app

RUN ./gradlew bootJar --no-daemon

# 実行用イメージ
FROM eclipse-temurin:21-jdk
WORKDIR /app
COPY --from=build /app/build/libs/*.jar app.jar

EXPOSE 8080
CMD ["java", "-jar", "app.jar"]