FROM node

WORKDIR /usr/src/app

COPY . .

RUN cd /usr/src/app

#RUN apt-get install npm -y

RUN npm install
RUN npm install mysql2 --save

ENV DOCKERIZE_VERSION v0.8.0

RUN apt-get update \
    && apt-get install -y wget \
    && wget -O - https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz | tar xzf - -C /usr/local/bin \
    && apt-get autoremove -yqq --purge wget && rm -rf /var/lib/apt/lists/*

EXPOSE 3000

# CMD ["node", "index.js"]