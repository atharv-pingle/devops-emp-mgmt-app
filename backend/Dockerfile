FROM golang:1.19 AS build
WORKDIR /app
COPY . .
RUN go mod tidy
RUN go build -o backend main.go

FROM alpine:latest
WORKDIR /root/
COPY --from=build /app/backend .
EXPOSE 8080
CMD ["./backend"]
