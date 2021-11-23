FROM golang:1.17.3-alpine3.14

WORKDIR /go/src/app

COPY . .

EXPOSE 4001 
ENV PORT=4001

RUN go build 

CMD [ "./vuego-demoapp" ]