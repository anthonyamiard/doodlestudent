FROM node:12-alpine AS build
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install
RUN npm install -g @angular/cli
COPY . .
RUN ng build --prod

FROM nginx:latest
COPY --from=build /usr/src/app/dist/tlcfront /usr/share/nginx/html
