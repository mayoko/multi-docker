FROM node:alpine

USER node

WORKDIR '/home/app'
COPY --chown=node ./package.json ./
RUN npm install
COPY --chown=node . .
CMD ["npm", "run", "start"]
