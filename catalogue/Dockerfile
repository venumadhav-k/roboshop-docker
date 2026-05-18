FROM node:20
#Creates and moves to /app
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install
ENV  MONGO="true" \
     MONGO_URL="mongodb://mongodb>:27017/catalogue"
CMD ["node", "server.js"]