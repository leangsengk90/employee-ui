FROM node:12.21-alpine as build
WORKDIR /app
COPY ./ ./
RUN npm install
RUN npm run build --prod

FROM nginx:alpine
COPY --from=build /app/dist/my-app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
