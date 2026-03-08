# Stage 1 : build Angular
FROM node:18 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2 : serveur de production
FROM nginx:alpine
COPY --from=builder app/dist/mon_premier_projet /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
