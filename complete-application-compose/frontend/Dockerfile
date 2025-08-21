
FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json .

RUN npm install

COPY frontend/ .

RUN npm run build

FROM nginx:stable-alpine

COPY --from=builder /app/build/ /usr/share/nginx/html
