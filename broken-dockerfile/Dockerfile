FROM alpine:3.18 AS builder

RUN echo "meu app" > /app

FROM scratch

COPY --from=builder /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/ca-certificates.crt
COPY --from=builder /app /app

CMD ["/app"]