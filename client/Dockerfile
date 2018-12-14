FROM node:8.14-stretch

WORKDIR /usr/src/app
COPY package*.json ./

RUN npm install -qy

COPY . . 

EXPOSE 3000

CMD ["npm", "run start"]