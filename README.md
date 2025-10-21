# Dockerized Go Web Application

A simple Go web application that demonstrates containerization with Docker. This application serves a simple HTTP server on port 8080 and responds with a "Hello from Dockerized Go app!" message.

## 🚀 Features

- Simple HTTP web server
- Containerized with Docker
- Multi-stage Docker build for optimized image size
- Available on Docker Hub

## 📋 Prerequisites

- [Go 1.20+](https://golang.org/dl/) (for local development)
- [Docker](https://www.docker.com/get-started) (for containerization)
- [Git](https://git-scm.com/) (for version control)

## 🏗️ Local Development

### Running without Docker

```bash
# Clone the repository
git clone https://github.com/Ali-Ashraf-510/my-go-app.git
cd my-go-app

# Run the application
go run main.go
```

The application will be available at `http://localhost:8080`

### Running with Docker

```bash
# Build the Docker image
docker build -t my-go-app .

# Run the container
docker run -p 8080:8080 my-go-app
```

## 🐳 Docker Hub

The Docker image is publicly available on Docker Hub:

**Docker Hub Repository:** [aliashraf510/my-go-app](https://hub.docker.com/r/aliashraf510/my-go-app)

### Pull and Run from Docker Hub

```bash
# Pull the image from Docker Hub
docker pull aliashraf510/my-go-app:latest

# Run the container
docker run -p 8080:8080 aliashraf510/my-go-app:latest
```

## 📁 Project Structure

```
.
├── main.go           # Main Go application
├── go.mod           # Go module file
├── Dockerfile       # Docker configuration
├── .dockerignore    # Docker ignore file
└── README.md        # Project documentation
```

## 🔧 Docker Build Process

This project uses a multi-stage Docker build for optimization:

1. **Build Stage**: Uses `golang:1.20-alpine` to compile the Go application
2. **Runtime Stage**: Uses `alpine:latest` with only the compiled binary for a smaller final image

### Build Commands

```bash
# Build the image with a tag
docker build -t my-go-app:latest .

# Build with a specific tag for Docker Hub
docker build -t aliashraf510/my-go-app:latest .

# Tag an existing image for Docker Hub
docker tag my-go-app:latest aliashraf510/my-go-app:latest
```

## 📤 Pushing to Docker Hub

```bash
# Login to Docker Hub
docker login

# Push the image
docker push aliashraf510/my-go-app:latest
```

## 🧪 Testing

Test the application by accessing:
- `http://localhost:8080` - Should display "Hello from Dockerized Go app!"

### Using curl

```bash
curl http://localhost:8080
```

Expected response:
```
Hello from Dockerized Go app!
```

## 📝 Environment Variables

Currently, this application doesn't use environment variables, but you can extend it by:

```bash
# Example of running with environment variables
docker run -p 8080:8080 -e ENV=production aliashraf510/my-go-app:latest
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Ali Ashraf**
- GitHub: [@Ali-Ashraf-510](https://github.com/Ali-Ashraf-510)
- Docker Hub: [aliashraf510](https://hub.docker.com/u/aliashraf510)

## 🔗 Links

- [Docker Hub Image](https://hub.docker.com/r/aliashraf510/my-go-app)
- [GitHub Repository](https://github.com/Ali-Ashraf-510/my-go-app)

---

*Built with ❤️ using Go and Docker*