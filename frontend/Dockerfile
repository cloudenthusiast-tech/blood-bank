# Stage 1: Build the React app
FROM node:20.19.6-alpine3.23 AS build
WORKDIR /opt/server
COPY *.json .
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine
WORKDIR /opt/server
COPY --from=build /opt/server/build /usr/share/nginx/html
CMD ["nginx", "-g", "daemon off;"]