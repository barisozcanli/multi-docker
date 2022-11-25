FROM node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN mpn installCOPY . .
RUN npm run builder
FROM nginxEXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html