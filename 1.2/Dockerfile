FROM golang:1.12.5-alpine AS build
WORKDIR $GOPATH/src/app/

RUN go get -d -v ./...
COPY *.go ./
RUN CGO_ENABLED=0 GOOS=linux go build \
    -a -installsuffix cgo -o /app . && \
    chmod 755 /app


FROM alpine:3.9
RUN apk add ca-certificates
COPY --from=build /app/ /app/
COPY form.html /static/form.html

EXPOSE 8080

CMD ["/app/app"]
