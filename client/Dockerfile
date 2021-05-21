FROM node:alpine as builder

USER node

WORKDIR '/home/app'
COPY --chown=node ./package.json ./
RUN npm install
COPY --chown=node . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /home/app/build /usr/share/nginx/html