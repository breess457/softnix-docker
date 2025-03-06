FROM node:20 AS build

RUN mkdir -p /app

WORKDIR /app

RUN git clone https://github.com/breess457/softnix-ui.git

WORKDIR /app/softnix-ui

RUN ls -l

COPY package*.json ./

RUN npm install --legacy-peer-deps

RUN npm run build

 FROM nginx:alpine

 COPY --from=build /app/softnix-ui/dist /usr/share/nginx/html

 COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
