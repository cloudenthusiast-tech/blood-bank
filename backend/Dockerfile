FROM node:20.19.6-alpine3.23 AS build
WORKDIR /opt/server
COPY *.json .
RUN npm install
COPY . .
RUN npm run build

FROM node:20.19.6-alpine3.23
WORKDIR /opt/server
COPY --from=build /opt/server /opt/server
CMD ["server.js"]
ENTRYPOINT ["node"]
