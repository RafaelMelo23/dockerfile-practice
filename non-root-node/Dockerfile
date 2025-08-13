
FROM node:18-alpine

WORKDIR /home/node/app

RUN adduser -D nodeuser

COPY package.json .
COPY index.js .

RUN chown -R nodeuser:nodeuser /home/node/app
## Ou usar o copy diretamente com --chown=nodeuser:nodeuser COPY package*.json ./

USER nodeuser

RUN npm install

EXPOSE 3000

CMD ["node", "index.js"]