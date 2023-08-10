FROM node:20-alpine3.18 as builder

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["npm", "run", "start"]

FROM nginx
EXPOSE 3000
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY --from=builder /app/build /usr/share/nginx/html