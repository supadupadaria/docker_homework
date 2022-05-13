FROM node:16-alpine as builder
WORKDIR /frontend
COPY . .
RUN npm install && npm run build

FROM nginx:alpine
COPY --from=builder /frontend/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
CMD ["nginx", "-g", "daemon off;"]
