
FROM eclipse-temurin:17-jdk-alpine as extractor

WORKDIR /app

COPY target/app.jar .

RUN java -Djarmode=layertools -jar app.jar extract

FROM gcr.io/distroless/java17-debian11

WORKDIR /app

COPY --from=extractor dependencies/ .
COPY --from=extractor spring-boot-loader/ .
COPY --from=extractor snapshot-dependencies/ .
COPY --from=extractor application/ .

USER nonroot

ENTRYPOINT ["java", "org.springframework.boot.loader.JarLauncher"]
