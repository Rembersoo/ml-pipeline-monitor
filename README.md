# 🧠 ML Pipeline Monitor

> A full-stack observability dashboard for machine learning models in production — think Datadog, but built by you, for ML.
>
> ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
> ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
> ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
> ![Apache Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
> ![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)
> ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
> ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
> ![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
>
> ---
>
> ## 📌 Project Overview
>
> **ML Pipeline Monitor** is a production-grade, end-to-end observability platform for machine learning systems. It simulates a live ML model (fraud detection / churn prediction), streams predictions through Apache Kafka, logs metrics to PostgreSQL, tracks experiments with MLflow, and visualizes everything on a real-time React dashboard.
>
> Built to demonstrate full-stack engineering + MLOps capabilities — from raw data to interactive dashboard.
>
> ---
>
> ## 🏗️ Architecture
>
> ```
> [ML Model Simulator (FastAPI)]
>         │
>         ▼ predictions (REST)
> [Apache Kafka Producer]
>         │
>         ▼ streaming events
> [Python Kafka Consumer]
>         │
>         ├──► PostgreSQL  (metrics: accuracy, latency, drift)
>         └──► MLflow      (experiments, model versions, hyperparameters)
>                 │
>                 ▼
>         [Node.js API Layer]
>                 │
>                 ▼
>         [React Dashboard]
>         (live charts, drift alerts, model comparison)
> ```
>
> ---
>
> ## ✨ Features
>
> - 🔴 **Real-time streaming** — Kafka ingests ML predictions as they happen
> - - 📊 **Live dashboard** — Accuracy over time, request throughput, P95 latency
>   - - 🚨 **Drift detection** — Alerts when model performance degrades below threshold
>     - - 🧪 **Experiment tracking** — MLflow stores model versions, hyperparameters, and performance snapshots
>       - - 🔍 **Model comparison** — Side-by-side view of multiple deployed model versions
>         - - 🐳 **Fully Dockerized** — One command to spin up the entire stack
>          
>           - ---
>
> ## 🚀 Build Phases
>
> ### Phase 01 — ML Model Simulator
> Simulate a live fraud detection / churn prediction model that emits predictions via a FastAPI REST endpoint. Generates synthetic data with configurable drift patterns.
>
> ### Phase 02 — Kafka Data Pipeline
> Kafka producer publishes predictions in real time. A Python consumer reads the stream and logs metrics (accuracy, latency, prediction confidence, drift score) to PostgreSQL.
>
> ### Phase 03 — MLflow Experiment Tracking
> Integrate MLflow to store model versions, hyperparameters, and performance snapshots. Enables reproducibility and historical comparison.
>
> ### Phase 04 — Node.js API Layer
> REST API built with Express.js that aggregates pipeline metrics from PostgreSQL and serves structured JSON to the frontend. Includes WebSocket support for live updates.
>
> ### Phase 05 — React Dashboard
> Interactive frontend with:
> - 📈 Accuracy & F1-score over time (Recharts)
> - - ⚡ Request throughput & latency heatmap
>   - - 🔔 Drift alert panel with configurable thresholds
>     - - 🗂️ Model version comparison table (MLflow integration)
>      
>       - ---
>
> ## 🗂️ Project Structure
>
> ```
> ml-pipeline-monitor/
> ├── model-simulator/        # FastAPI — fake fraud/churn ML model
> │   ├── main.py
> │   ├── model.py
> │   └── requirements.txt
> ├── pipeline/               # Kafka producer + Python consumer
> │   ├── producer.py
> │   ├── consumer.py
> │   └── drift_detector.py
> ├── mlflow-tracking/        # MLflow experiment configs
> │   └── experiments/
> ├── api/                    # Node.js + Express REST API
> │   ├── src/
> │   │   ├── routes/
> │   │   └── db/
> │   └── package.json
> ├── dashboard/              # React frontend
> │   ├── src/
> │   │   ├── components/
> │   │   │   ├── AccuracyChart.jsx
> │   │   │   ├── DriftAlert.jsx
> │   │   │   ├── ThroughputChart.jsx
> │   │   │   └── ModelComparison.jsx
> │   │   └── App.jsx
> │   └── package.json
> ├── docker-compose.yml
> └── README.md
> ```
>
> ---
>
> ## ⚙️ Tech Stack
>
> | Layer | Technology |
> |---|---|
> | ML Model Simulator | Python, FastAPI |
> | Streaming | Apache Kafka |
> | Metrics Storage | PostgreSQL |
> | Experiment Tracking | MLflow |
> | System Metrics | Prometheus |
> | API Layer | Node.js, Express.js |
> | Frontend | React, Recharts |
> | Infrastructure | Docker, Docker Compose |
>
> ---
>
> ## 🛠️ Getting Started
>
> ### Prerequisites
> - Docker & Docker Compose
> - - Node.js >= 18
>   - - Python >= 3.10
>    
>     - ### Run the full stack
>    
>     - ```bash
>       git clone https://github.com/Rembersoo/ml-pipeline-monitor.git
>       cd ml-pipeline-monitor
>       docker-compose up --build
>       ```
>
> | Service | URL |
> |---|---|
> | React Dashboard | http://localhost:3000 |
> | Node.js API | http://localhost:4000 |
> | FastAPI Model Simulator | http://localhost:8000/docs |
> | MLflow UI | http://localhost:5000 |
> | Prometheus | http://localhost:9090 |
>
> ---
>
> ## 📸 Screenshots
>
> > 🚧 Coming soon — dashboard UI in progress
> >
> > ---
> >
> > ## 🎯 Recruiter Highlights
> >
> > - ✅ **End-to-end ownership** — Data ingestion → pipeline → API → UI
> > - - ✅ **Real-time streaming** — Apache Kafka for live prediction events
> >   - - ✅ **MLOps practices** — Drift detection, experiment versioning, model comparison
> >     - - ✅ **Production patterns** — Dockerized microservices, REST + WebSocket APIs
> >       - - ✅ **Full stack** — Python (FastAPI) + Node.js + React in one cohesive system
> >        
> >         - ---
> >
> > ## 👩‍💻 Author
> >
> > **Sri Vani Rembersoo**
> > Full Stack Software Engineer | AWS Certified Developer | Transitioning into AI/ML
> >
> > [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sri-vani-rembersoo-267139224/)
> > [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Rembersoo)
> >
> > ---
> >
> > ## 📄 License
> >
> > MIT License © 2025 Sri Vani Rembersoo
