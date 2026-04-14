#stage 1 build the mood backend
FROM node:20-alpine AS builder

WORKDIR /app

COPY package.json .

RUN npm install

#stage 2 copy the build files and run the app
FROM node:20-alpine

WORKDIR /app

COPY --from=builder /app/node_modules /app/node_modules

COPY . .

EXPOSE 8082

CMD ["npm", "start"]