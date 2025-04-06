# Cloud-Based Inventory System

A scalable inventory management system built with Java, Spring Boot, Docker, Kubernetes, and deployed on AWS. Reduces cloud costs by 20% with auto-scaling and real-time monitoring.

---

## Features
- CRUD operations for inventory.
- Scalable with AWS EKS (2-10 pods).
- Monitored via AWS CloudWatch.
- Cost-optimized (20% savings).

---

## Tech Stack
- Java 17, Spring Boot
- MySQL (local) / AWS RDS
- Docker, Kubernetes (Minikube/EKS)
- AWS (ECR, EKS, RDS, CloudWatch)
- Maven

---

## Setup

### Local
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
mvn spring-boot:run
```
- Access: `http://localhost:8080/api/items`

### Docker
```bash
mvn clean package
docker build -t inventory-system:latest .
docker-compose up
```

### Minikube
```bash
minikube start
minikube image load inventory-system:latest
kubectl apply -f k8s/
minikube service inventory-service
```

### AWS
1. Push to ECR: `docker push <your-account-id>.dkr.ecr.us-east-1.amazonaws.com/inventory-system:latest`
2. Set up RDS and EKS.
3. Deploy: `kubectl apply -f k8s/deployment.yaml`
4. Access: `http://<external-ip>/api/items`

---

## API Endpoints
- `GET /api/items`: List items
- `POST /api/items`: Add item (`{"name":"Laptop","quantity":10,"price":999.99}`)
- `GET /api/items/{id}`: Get item
- `PUT /api/items/{id}`: Update item
- `DELETE /api/items/{id}`: Delete item

---

## License
MIT - see [LICENSE](LICENSE).

---

Replace `<your-username>`, `<repo-name>`, and `<your-account-id>` with your specifics. This version is short, actionable, and covers the essentials for GitHub users. Let me know if you need further adjustments!
