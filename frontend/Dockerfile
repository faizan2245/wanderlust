FROM node:21 AS frontend-builder
WORKDIR /app
COPY . .
RUN npm i

FROM node:21-slim
WORKDIR /app
COPY  --from=frontend-builder- /app .
COPY  .env.docker .env.local
EXPOSE 5173

CMD ["npm", "run","dev","--", "--host"]
