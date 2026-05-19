FROM node:20.20.2-alpine3.22 AS builder
 WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install


FROM node:20.20.2-alpine3.22
WORKDIR /app
COPY --from=builder /app /app
ENV  REDIS_HOST="redis" \
     CATALOGUE_HOST="catalogue" \
     CATALOGUE_PORT="8080"
CMD ["node", "server.js"]

# FROM node:20
# #Creates and moves to /app
# WORKDIR /app
# COPY package.json .
# COPY *.js .
# RUN npm install
# ENV  REDIS_HOST="redis" \
#      CATALOGUE_HOST="catalogue" \
#      CATALOGUE_PORT="8080"
# CMD ["node", "server.js"]