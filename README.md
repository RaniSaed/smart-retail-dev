# Smart Retail Inventory System

---

**A cloud-native inventory control platform for modern retail**  
Delivering real-time visibility, analytics, automated restocking, and built-in disaster recovery.

Built using **Flask**, **React**, **PostgreSQL**, **Docker**, **Kubernetes**, **Prometheus**, and **Grafana** — for a scalable, resilient, and developer-friendly architecture.

---

## Features

- **Inventory API** – CRUD operations for product management using Flask and PostgreSQL  
- **Restocking Automation** – Logs and tracks each stock update with audit trail  
- **Low-Stock Alerts** – Flags items that fall below defined thresholds  
- **Analytics Dashboard** – Visualizes inventory trends and product movement  
- **Purchase Workflow** – Deducts stock upon purchase in real time  
- **Dockerized Architecture** – Full container support via Docker & Compose  
- **Cloud-Native Deployment** – Kubernetes-ready with manifests and GitOps support  
- **Monitoring & Alerts** – Prometheus metrics, Grafana dashboards, and custom alerts

---

## Tech Stack

| Category           | Technologies                                             |
|--------------------|----------------------------------------------------------|
| Backend & API      | Python 3.9 · Flask · Flask-RESTful                       |
| Frontend           | React · TypeScript · Tailwind CSS · React Query          |
| Database           | PostgreSQL                                               |
| Containerization   | Docker · Docker Compose                                  |
| Orchestration      | Kubernetes (Minikube)                                    |
| Monitoring         | Prometheus · Grafana · Alertmanager                      |

---

## Quick Start (Development)

```bash
# 1. Clone the repository
git clone https://github.com/RaniSaed/smart-retail-dev.git
cd smart-retail-dev/backend

# 2. Set up Python environment
python3 -m venv venv
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Start the API server
python app.py  # Visit: http://localhost:5000
```

---

## Docker Setup

### Backend Only

```bash
docker build -t rani19/backend .
docker run -p 5000:5000 rani19/backend
```

### Full Stack with Docker Compose

```bash
docker-compose up
```

Services included:
- Flask backend (API)
- PostgreSQL database
- React frontend (User Panel)
- pgAdmin (Database GUI)

---

## API Reference

### `/api/products`

| Method | Description                       |
|--------|-----------------------------------|
| GET    | Retrieve all products             |
| POST   | Create a new product              |

### `/api/products/<id>`

| Method | Description                          |
|--------|--------------------------------------|
| GET    | Get product details by ID            |
| PUT    | Update product information by ID     |
| DELETE | Remove product from inventory by ID  |

### `/api/products/<id>/restock`

| Method | Description                                |
|--------|--------------------------------------------|
| POST   | Add restock quantity and log the event     |

### Analytics & Monitoring

| Endpoint                      | Description                               |
|-------------------------------|-------------------------------------------|
| `/api/products/low-stock`     | List of low-stock products                |
| `/api/analytics/stock-trends` | Inventory trend data                      |
| `/metrics`                    | Prometheus metrics for monitoring         |
| `/health`                     | Health check endpoint                     |

---

## Kubernetes Deployment

```bash
kubectl apply -f k8s/
kubectl get all -l app=smart-retail-backend
```

This deploys:
- Deployments
- Services
- ConfigMaps
- Ingress resources

---

## Monitoring & Alerting

| Component         | Tool            | Description                                     |
|-------------------|------------------|-------------------------------------------------|
| API Metrics       | Prometheus       | Monitors request count, latency, and errors     |
| System Metrics    | Node Exporter    | Tracks CPU, memory, and disk usage              |
| Low-Stock Alerts  | Custom Exporter  | Detects when stock is below threshold           |
| Dashboards        | Grafana          | Visualizes metrics via interactive panels       |
| Notifications     | Alertmanager     | Sends email alerts for critical conditions      |

---

## Repository Structure

```
smart-retail-dev/
├── backend/
│   ├── app.py             # Flask API with all endpoints
│   ├── models.py          # SQLAlchemy models: Product, RestockLog
│   ├── app_config.py      # Environment and DB configuration
│   ├── Dockerfile         # Backend Docker build
│   ├── requirements.txt   # Python dependencies
│   └── seed.py            # Optional DB seeding script
│
├── frontend/
│   ├── src/               # React components (TSX)
│   ├── Dockerfile         # Frontend container build
│   └── vite.config.ts     # Vite config and proxy setup
│
├── scripts/
│   ├── failover-check.sh  # DR failover monitoring script
│   ├── start-dev.sh       # Dev environment setup (e.g. port forwarding)
│   └── auto-forward.sh    # Auto-forwarding helper
│
├── docker-compose.yml     # Full stack orchestration
└── README.md              # Project documentation
```

---

## Useful Links

- Dev Repository: [https://github.com/RaniSaed/smart-retail-dev](https://github.com/RaniSaed/smart-retail-dev)  
- Docker Hub: [https://hub.docker.com/u/rani19](https://hub.docker.com/u/rani19)

---

## Author

**Rani Saed**  
DevOps Engineer | Cloud & Kubernetes Enthusiast  
Email: [Rani.saed19@gmail.com](mailto:Rani.saed19@gmail.com)  
LinkedIn: [https://www.linkedin.com/in/rani-saed](https://www.linkedin.com/in/rani-saed)
