FROM node as node
WORKDIR /app
COPY package.json /app/
RUN npm i npm@latest -g
RUN npm install
COPY ./ /app/
RUN npm run build

FROM nginx:alpine

COPY --from=node app/dist/web /usr/share/nginx/html

EXPOSE 80
