# Use the official golang image as the base image
FROM golang:latest

# Set the Current Working Directory inside the container
WORKDIR /app

# Copy go mod and sum files
COPY go.mod go.sum ./

# Download all dependencies. Dependencies will be cached if the go.mod and go.sum files are not changed
RUN go mod download

# Copy the source code into the container
COPY . .

# Build the Go app
RUN go build -o main .

# Command to run the executable
CMD DB_HOST=172.17.0.2 DB_USER=postgres DB_PASSWORD=postgres DB_NAME=postgres DB_PORT=5432 ALLOWED_ORIGINS=* go run main.go
