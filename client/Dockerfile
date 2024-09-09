
FROM node AS build

WORKDIR /app

RUN npm install -g @angular/cli

COPY package*.json ./
RUN npm install
COPY . .
RUN ng build library-management-system -c production

FROM nginx:alpine

COPY --from=build /app/dist/library-management-system /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
