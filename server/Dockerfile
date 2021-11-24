# Container for the backend

# Importing the golang image from DockerHub
FROM golang:1.17.3-alpine3.14

# Set the working directory of the container
WORKDIR /go/src/app

# Copy files from the server folder to the working directory inside container
COPY . .

# Set port 4001 for all requests
EXPOSE 4001 
ENV PORT=4001

# Command to build the go project
RUN go build 

# Execute the previous command 
CMD [ "./vuego-demoapp" ]