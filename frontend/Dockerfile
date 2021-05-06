#Image and main folder
FROM node:14-alpine
RUN mkdir /app
WORKDIR /app

#Copy Files
COPY package*.json ./

#Environments
ENV PATH /app/node_modules/.bin:$PATH
EXPOSE 3000

#Dependencies
RUN npm install --nocache

#Copy and commands
COPY . .
CMD [ "npm", "start" ]