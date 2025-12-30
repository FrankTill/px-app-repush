# px-app-repush

## Deployment

To run in production:

1. Build Docker image: `docker build -t px-app-repush .`
2. Run with environment: `docker run -p 5000:5000 --env-file .env px-app-repush`

Or use Docker Compose: `docker-compose up --build`

Or use gunicorn directly: `gunicorn --bind 0.0.0.0:5000 app:app`

Ensure .env is set with production values.