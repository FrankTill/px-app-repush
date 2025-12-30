# px-app-repush

## Deployment

To run in production:

1. Create required directories:
   ```bash
   mkdir -p csv_output logs
   ```

2. Build and run with Docker Compose:
   ```bash
   docker compose -f docker-compose-example.yml up --build
   ```

3. Access the app at http://localhost:5020

Or use Docker directly:
```bash
docker build -t px-app-repush .
docker run -p 5020:5000 --env-file .env -v ./csv_output:/app/csv_output -v ./logs:/app/logs px-app-repush
```

Or use gunicorn directly:
```bash
gunicorn --bind 0.0.0.0:5000 app:app
```

Ensure .env is set with production values.