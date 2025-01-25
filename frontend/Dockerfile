# Etapa de producción
FROM node:16-alpine AS build
WORKDIR /app

COPY . .
RUN npm install
RUN npm run build --prod
# Serve Application using Nginx Server
FROM nginx:alpine 
COPY --from=build /app/dist/optica-app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
