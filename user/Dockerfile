FROM node:20.20.2-alpine3.22 AS builder
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install



FROM node:20.20.2-alpine3.22
WORKDIR /app
COPY --from=builder /app /app
ENV  MONGO="true" \
     MONGO_URL="mongodb://mongodb:27017/catalogue" \
     REDIS_URL="redis://redis:6379"
CMD ["node", "server.js"]


# FROM node:20
# #Creates and moves to /app
# WORKDIR /app
# COPY package.json .
# COPY *.js .
# RUN npm install
# ENV  MONGO="true" \
#      MONGO_URL="mongodb://mongodb:27017/catalogue" \
#      REDIS_URL="redis://redis:6379"
# CMD ["node", "server.js"]