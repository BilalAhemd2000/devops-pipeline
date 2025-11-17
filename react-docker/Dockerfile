FROM node:20-alpine

# create a user group other than root to run the container
RUN addgroup app && adduser -S -G app app

# switch to user app
USER app

WORKDIR /app

COPY package*.json ./

USER root

RUN chown -R app:app .

USER app

RUN npm install

COPY . .

EXPOSE 5173

CMD npm run dev
