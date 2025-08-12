
FROM eclipse-temurin:17-jre-alpine

WORKDIR /app

COPY target/app.jar .

ENV PROFILE_ATIVO=producao

CMD ["java", "-jar", "app.jar"]