
FROM node:14 as build
RUN git clone https://github.com/StefanLocke/doodlestudent.git
WORKDIR /doodlestudent/front

RUN npm install
RUN npm run build

FROM nginx:1.17.1-alpine as nginx
COPY --from=build /doodlestudent/front/dist/tlcfront /usr/share/nginx/html
EXPOSE 80


