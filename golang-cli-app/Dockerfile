
FROM golang:1.21-alpine as builder

WORKDIR /app

COPY main.go .

RUN go build -o /meu-app .

FROM scratch

WORKDIR /app

LABEL maintainer="whatever" \
      description="Golang CLI app"

COPY --from=builder /meu-app /meu-app

ENTRYPOINT ["/meu-app"]

CMD ["--help"]
