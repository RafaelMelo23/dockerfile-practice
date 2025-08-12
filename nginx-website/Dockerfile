
FROM nginx:alpine

WORKDIR /usr/share/nginx/html

COPY index.html ./

COPY . .

CMD ["nginx", "-g", "daemon off;"]