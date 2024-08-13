### Build
FROM beevelop/ionic:v2021.06.1 AS ionic
# FROM beevelop/ionic:latest AS ionic
## Create app directory
WORKDIR /usr/src/app
## Install app dependencies
## A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./
ENV NODE_OPTION="--openssl-legacy-provider"
RUN echo "Varibale $NODE_OPTION"
RUN npm install -f
## Bundle app source
COPY . .
RUN ionic build
### Run 
FROM nginx:alpine
RUN rm -rf /usr/share/nginx/html/*
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html