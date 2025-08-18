
FROM eclipse-temurin:17-jre-alpine AS builder

WORKDIR /build

COPY app.jar .

FROM gcr.io/distroless/java17-debian11

WORKDIR /app

USER nonroot

COPY --from=builder /build/app.jar .

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]