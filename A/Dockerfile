FROM ubuntu:latest

RUN apt-get update
RUN apt-get install nodejs npm -y
RUN apt-get install -y mongodb
RUN ln -s /usr/bin/nodejs /usr/local/bin/node
RUN ln -s /usr/bin/npm /usr/local/bin/npm
RUN mkdir -p /data/db
#copie du package.json + lancement de l'installation
COPY * ./
RUN npm install

ENV NODE_ENV=development PORT=8080 MONGO_HOST=mongo MONGO_USER=user MONGO_DATABASE=test MONGO_PASSWORD=password MONGO_PORT=27017

EXPOSE 8080

CMD [ "npm", "start" ]
