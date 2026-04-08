FROM node:18

WORKDIR /app
COPY code/ .

RUN npm install

EXPOSE 5000

CMD ["node", "index.js"]