# Container for the front end

# Import the node image from DockerHub
FROM node:14-alpine

# Set the working directory of the container
WORKDIR /usr/src/app

# Copy all package...json that are in spa to the respective place
COPY package*.json ./

# Copy files from the spa folder to the working directory inside container
COPY . .

# Set VUE_APP_API_ENDPOINT for the front end
RUN echo "VUE_APP_API_ENDPOINT=\"http://localhost:4001/api\"" > .env.production

# Install yarn dependencies including vue.cli
RUN yarn

# Build app
RUN yarn build

# Import nginx image to be able to execute the website
FROM nginx:stable-alpine
COPY --from=0 usr/src/app/dist /usr/share/nginx/html

# Set port 80 for requests
EXPOSE 80