FROM node:lts-alpine

# install simple http server for serving static content
RUN npm install -g http-server

# make the 'app' folder the current working directory
WORKDIR /app

# copy both 'package.json' and 'package-lock.json' (if available)
COPY ./vue-retirement/package*.json ./

# install project dependencies
RUN npm install

# copy project files and folders to the current working directory (i.e. 'app' folder)
COPY ./vue-retirement .

# build app for production with minification
RUN npm run build && mkdir dist/retirement && cp -r dist/js dist/retirement && cp -r dist/css dist/retirement

EXPOSE 8080
CMD [ "http-server", "dist" ]
