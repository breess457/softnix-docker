FROM node:20

WORKDIR /app

RUN npm install -g npm@6

RUN git config --global http.postBuffer 524288000 \
    && git clone https://github.com/breess457/softnix-backend.git

RUN ls -l /app

# COPY package*.json ./

RUN npm install -g npm@6

RUN npm cache clean --force

RUN rm -rf node_modules package-lock.json

RUN npm install --legacy-peer-deps || cat /root/.npm/_logs/*.log

EXPOSE 3001

CMD ["npm", "start"]