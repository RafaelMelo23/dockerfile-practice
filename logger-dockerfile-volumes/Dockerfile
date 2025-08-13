
FROM alpine:latest

RUN mkdir -p "/app/logs"

VOLUME ["/app/logs"]

CMD while true; do date >> /app/logs/activity.log; sleep 5; done