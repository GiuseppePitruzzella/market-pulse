<br />
<div align="center">
  <a href="https://github.com/GiuseppePitruzzella/market-pulse">
    <img src="assets/images/logo.png" alt="Logo" width="300">
  </a>

  <h3 align="center">Market Pulse</h3>

  <p align="center">
    A real-time risk monitoring system for Exchange-Traded Funds (ETFs), built on a modern streaming data pipeline.
    <br />
    <a href="https://github.com/GiuseppePitruzzella/market-pulse/issues">Report Bug</a>
    ·
    <a href="https://github.com/GiuseppePitruzzella/market-pulse/issues">Request Feature</a>
  </p>
</div>


## 📘 Project Overview

**Market Pulse** is designed to overcome the limitations of traditional, static financial analysis. By leveraging a real-time data pipeline, this system captures, processes, and analyzes market data as it becomes available.

The goal is to provide portfolio managers and analysts with a dynamic dashboard that reveals critical risk insights, such as **Dynamic Tracking Error**, **Correlation Matrices**, and **Value at Risk (VaR)**. This enables faster, more informed decision-making based on live market conditions.


## 📦 Data Source Setup

This project does not use a static dataset. Instead, it consumes a **live data stream** from a real-time financial data provider.

To run the pipeline, you will need to obtain an API key from a service like [Polygon.io](https://polygon.io/) or [Finnhub](https://finnhub.io/). The key must be configured as an environment variable for the system to access market data.

## 🧪 Environment Setup

The entire pipeline is containerized using **Docker** and **Docker Compose** to ensure a consistent and reproducible environment.

Key dependencies are managed within their respective service containers:
- **Logstash**: Requires configuration of the `http_poller` input.
- **Spark**: Environment managed with its Docker image, including necessary connectors.
- **Kafka, Elasticsearch, Grafana**: Standard Docker images are used.

To run the project, you only need **Docker** and **Docker Compose** installed on your host machine.

---

## 📁 Project Structure

```bash
market-pulse/
├── grafana/
│   └── provisioning/      # Dashboards and datasources configs
├── logstash/
│   └── pipeline/
│       └── pipeline.conf      # Logstash ingestion pipeline
├── spark/
│   └── app/
│       └── main.py            # Spark Streaming application
├── .env.example           # Environment variables template
├── docker-compose.yml     # Main composition file for all services
├── .gitignore
└── README.md