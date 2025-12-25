# E-commerce Platform App

This folder contains the application code for the e-commerce platform, divided into backend and frontend components. Each component is containerized using Docker.

## Backend

The backend is a PHP API service.

### Building the Backend Image

```bash
cd backend
docker build -t ecommerce-backend .
```

### Running the Backend Container

```bash
docker run -p 8080:80 ecommerce-backend
```

## Frontend

The frontend is a PHP-based web interface.

### Building the Frontend Image

```bash
cd frontend
docker build -t ecommerce-frontend .
```

### Running the Frontend Container

```bash
docker run -p 80:80 ecommerce-frontend
```

## Deployment

For production deployment, refer to the Kubernetes manifests in the `k8s/` folder.
