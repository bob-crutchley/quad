FROM node:10 as node-build
WORKDIR /build
COPY . .
RUN npm install
RUN npm run build
FROM nginx
WORKDIR /app
COPY --from=node-build /build/build .
COPY nginx.conf /etc/nginx/nginx.conf
