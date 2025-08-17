
FROM eclipse-temurin:17-jre-alpine

ARG JAVA_OPTS=-Xmx256m
ENV JAVA_OPTS=${JAVA_OPTS}

WORKDIR /app

RUN adduser -D appuser

COPY --chown=appuser:appuser app.jar .

USER appuser

EXPOSE 8080

ENTRYPOINT ["/bin/sh", "-c"]

CMD ["exec java $JAVA_OPTS -jar app.jar"]



