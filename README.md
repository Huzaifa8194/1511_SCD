# Cafe Management System

A microservices-based cafe management system with automated CI/CD pipeline.

## Services

- API Gateway
- Payment Service
- Order Service
- Menu Service
- Inventory Service
- Customer Service

## CI/CD Pipeline

This project uses GitHub Actions for continuous integration and deployment. The pipeline automatically builds Docker images for each service and pushes them to Docker Hub whenever changes are pushed to the main branch.

### Setup Instructions

1. **Fork and Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/cafe-management-system.git
   cd cafe-management-system
   ```

2. **Set Up Docker Hub Secrets in GitHub**
   - Go to your GitHub repository
   - Navigate to Settings > Secrets and variables > Actions
   - Add the following secrets:
     - `DOCKERHUB_USERNAME`: Your Docker Hub username
     - `DOCKERHUB_TOKEN`: Your Docker Hub access token (not your password)

3. **Push Changes to GitHub**
   - Make changes to any service
   - Commit and push to the main branch
   - GitHub Actions will automatically build and push the Docker images

### Running the Application

1. **Set Environment Variable**
   ```bash
   export DOCKERHUB_USERNAME=your-dockerhub-username
   ```

2. **Start the Application**
   ```bash
   docker-compose up -d
   ```

3. **Access the Services**
   - API Gateway: http://localhost:3000
   - Payment Service: http://localhost:3001
   - Order Service: http://localhost:3002
   - Menu Service: http://localhost:3003
   - Inventory Service: http://localhost:3004
   - Customer Service: http://localhost:3005

## Development Workflow

1. Make changes to the code
2. Commit and push to the main branch
3. GitHub Actions will automatically build and push Docker images
4. Pull the latest images and restart the services:
   ```bash
   docker-compose pull
   docker-compose up -d
   ```

## Troubleshooting

- If the GitHub Actions workflow fails, check the Actions tab in your GitHub repository for error messages
- If Docker images fail to build, check the Docker Hub repository for error logs
- If services fail to start, check the Docker logs:
  ```bash
  docker-compose logs
  ``` 