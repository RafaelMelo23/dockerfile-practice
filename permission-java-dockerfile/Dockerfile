FROM eclipse-temurin:17-jre-alpine

WORKDIR /app

RUN adduser -D appuser

COPY --chown=appuser:appuser build/app.jar .
COPY --chown=appuser:appuser config/production.properties ./config/

USER appuser

WORKDIR /app

EXPOSE 8080

CMD ["java", "-Dspring.config.location=config/production.properties", "-jar", "app.jar"]