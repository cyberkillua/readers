# Go API Template Boilerplate

This repository is a boilerplate for building API projects in Go. It uses Go-chi for routing, SQLC for database interactions, and PostgreSQL as the database. Environment variables are managed with `godotenv`. This setup is tailored for my current use case and will evolve as I learn more about Go.

## Prerequisites

Ensure you have the following installed on your system:
- Go (latest version recommended)
- PostgreSQL
- SQLC
- Goose
- Air (for hot reloading)

## Commands

### Project Setup

```bash
# Initialize a new Go module
go mod init github.com/cyberkillua/go-api-template

# Clean up and download dependencies
go mod tidy

# Create a vendor directory for dependencies
go mod vendor
```

### Build and Run

```bash
# Build and run the application
go run cmd/main.go

# Build executable and run
go build -o readers cmd/main.go && ./readers
```

### Install Tools

```bash
# Install SQLC
go install github.com/sqlc-dev/sqlc/cmd/sqlc@latest 

# Install Goose for database migrations
go install github.com/pressly/goose/v3/cmd/goose@latest

# Install Air for hot reloading
go install github.com/air-verse/air@latest
```

### Adding Dependencies

```bash
# Add dotenv for environment variable management
go get github.com/joho/godotenv

# Add UUID generation library
go get github.com/google/uuid    

# Add PostgreSQL driver
go get github.com/lib/pq
```

### Using SQLC

To generate SQLC files from your queries:

```bash
sqlc generate
```

### Using Goose

To run database migrations:

```bash
goose postgres postgres://postgres:@localhost:5432/dbname up
```

### Using Air for Hot Reloading

To enable hot reloading during development:

```bash
air --build.cmd "go build -o bin/api cmd/main.go" --build.bin "./bin/api"
```

## Features

- **Routing**: Go-chi for lightweight and efficient HTTP routing
- **Environment Management**: godotenv for managing environment variables
- **Database**: PostgreSQL with SQLC for type-safe database access
- **Migrations**: Goose for managing database migrations

## Notes

This boilerplate reflects my current understanding of Go and is subject to change as I continue to learn and refine my approach. Feel free to adapt it to your own projects.