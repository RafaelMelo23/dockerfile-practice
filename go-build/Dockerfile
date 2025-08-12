
FROM golang:1.21-alpine as builder

WORKDIR /app

COPY . .
RUN go build -o meu-app .

FROM scratch

COPY --from=builder /app/meu-app /app

CMD ["/meu-app"]
