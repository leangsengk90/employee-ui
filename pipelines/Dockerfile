FROM node:12.21-alpine as BUILD
WORKDIR /app
COPY ./ ./
RUN npm install
RUN npm run build --prod

FROM nginx:alpine
COPY --from=BUILD /app/dist/my-app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
