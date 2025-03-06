FROM node:20

WORKDIR /app

RUN git clone https://github.com/breess457/softnix-ui.git

WORKDIR /app/softnix-ui

RUN ls -l

# COPY package*.json ./

RUN npm install --legacy-peer-deps

RUN npm run build

EXPOSE 5173

CMD ["npm","run", "dev"]
