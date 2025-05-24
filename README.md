# DevOps Project: Microservices Architecture with AWS, Docker, and GitLab CI/CD

## Project Overview
This project implements a microservices-based architecture using Docker containers, AWS infrastructure, and GitLab CI/CD pipeline. The system consists of multiple services that work together to provide a scalable and maintainable application.

## Project Structure
```
.
├── frontend/           # Frontend application
├── nginx/             # Nginx configuration and reverse proxy
├── backend_rds/       # Backend service with PostgreSQL database
├── backend_redis/     # Backend service with Redis cache
├── docker-compose.yml # Docker services configuration
└── .gitlab-ci.yml     # GitLab CI/CD pipeline configuration
```

## Services

### Frontend Service
- Located in the `frontend/` directory
- Serves the user interface
- Configured to work with the backend services

### Backend Services
1. **Backend RDS Service**
   - Port: 8000
   - Integrates with PostgreSQL database
   - Environment variables for database configuration
   - CORS configuration for frontend communication

2. **Backend Redis Service**
   - Port: 8001
   - Integrates with Redis cache
   - Environment variables for Redis configuration
   - CORS configuration for frontend communication

### Database Services
1. **PostgreSQL**
   - Version: 13
   - Port: 5432
   - Persistent volume for data storage
   - Environment variables for database credentials

2. **Redis**
   - Version: Alpine
   - Port: 6379
   - Password-protected
   - Used for caching and session management

### Nginx
- Acts as a reverse proxy
- Handles routing between services
- Located in the `nginx/` directory

## Infrastructure

### Docker
- Containerized services using Docker
- Docker Compose for service orchestration
- Custom network configuration for service communication
- Volume management for data persistence

### AWS Integration
- CloudFront distribution for content delivery
- RDS for managed PostgreSQL database
- Elasticache for managed Redis service
- S3 for static file storage

### GitLab CI/CD
- Automated build and deployment pipeline
- Environment-specific configurations
- Automated testing
- Deployment to AWS infrastructure

## Environment Variables
The project uses the following environment variables:
- `SECRET_KEY`: Application secret key
- `DEBUG`: Debug mode flag
- `DB_NAME`: PostgreSQL database name
- `DB_USER`: PostgreSQL user
- `DB_PASSWORD`: PostgreSQL password
- `REDIS_DB`: Redis database number
- `REDIS_PASSWORD`: Redis password
- `CORS_ALLOWED_ORIGINS`: Allowed origins for CORS

## Getting Started

1. Clone the repository
2. Configure environment variables
3. Run `docker-compose up` to start all services
4. Access the application through the configured domain

## Development
- Use Docker for local development
- Follow the GitLab CI/CD pipeline for deployments
- Maintain environment variables in secure storage
- Follow the branching strategy defined in the CI/CD configuration

## Security
- All services are password-protected
- CORS is properly configured
- Environment variables are used for sensitive data
- Network isolation using Docker networks

## Contributing
1. Create a new branch for your feature
2. Make your changes
3. Submit a merge request
4. Ensure CI/CD pipeline passes
5. Get code review approval

## License
This project is proprietary and confidential.

