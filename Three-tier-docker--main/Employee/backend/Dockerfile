# Stage 1: Build the Go application
FROM golang:1.20 AS builder

# Set the Current Working Directory inside the container
WORKDIR /backend

# Copy Go Modules manifests
COPY go.mod go.sum ./

# Download all dependencies. Dependencies will be cached if the go.mod and go.sum files are not changed
RUN go mod download

# Copy the source code into the container
COPY . .

# Build the Go application
RUN go build -o myapp .

# Stage 2: Create a minimal image to run the application
FROM ubuntu:latest

# Install necessary packages
RUN apt-get update && \
    apt-get install -y \

# Set the Current Working Directory inside the container
WORKDIR /backend

# Copy the binary from the builder stage
COPY --from=builder /backend/myapp .

# Expose the port the application will run on
EXPOSE 8080

# Command to run the executable
CMD ["./myapp"]