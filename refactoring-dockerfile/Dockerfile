# Estágio de Build
FROM node:18-alpine AS builder

WORKDIR /app

COPY package.json .
RUN npm install

COPY . .

RUN npm run build

# Estágio Final
FROM nginx:stable-alpine
COPY --from=builder /app/build /usr/share/nginx/html
# Doenst need a set cmd command, as nginx already has one that starts it once on.