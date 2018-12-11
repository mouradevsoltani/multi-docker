FROM node:alpine as bulider
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run bulid

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=bulider /app/bulid /usr/share/nginx/html