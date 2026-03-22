📌 K City Centre Mall Monitoring & Logging System
🚀 Project Overview

This project implements a centralized monitoring and logging system for infrastructure using:

Prometheus (Metrics collection)

Grafana (Visualization)

Elasticsearch (Log storage)

Logstash (Log processing)

Kibana (Log visualization)

It enables real-time monitoring, log analysis, and alerting, ensuring high system reliability and faster issue resolution.

🏗️ Architecture
             +----------------------+
             |   Linux Server       |
             | (System + App Logs)  |
             +----------+-----------+
                        |
        +---------------+----------------+
        |                                |
        v                                v
+-------------------+          +-------------------+
|  Node Exporter    |          |     Logstash      |
| (System Metrics)  |          | (Log Processing)  |
+--------+----------+          +--------+----------+
         |                              |
         v                              v
+-------------------+          +-------------------+
|   Prometheus      |          |  Elasticsearch    |
| (Metrics Store)   |          | (Log Storage)     |
+--------+----------+          +--------+----------+
         |                              |
         v                              v
+-------------------+          +-------------------+
|     Grafana       |          |      Kibana       |
| (Dashboards)      |          | (Log Analysis)    |
+-------------------+          +-------------------+
📊 Features

✅ Real-time system monitoring (CPU, Memory, Disk, Network)
✅ Centralized log collection and analysis
✅ Interactive dashboards using Grafana
✅ Log search and filtering using Kibana
✅ Secure communication (HTTPS + authentication)
✅ Alerting using Prometheus rules

🛠️ Tech Stack
Category	Tools
Monitoring	Prometheus
Visualization	Grafana
Logging	Logstash
Storage	Elasticsearch
UI	Kibana
OS	Ubuntu Linux
⚙️ Setup Instructions
1. Install Monitoring Stack

Install Prometheus & Node Exporter

Configure prometheus.yml

2. Install Grafana

Add Prometheus as data source

Import dashboard (ID: 1860)

3. Setup ELK Stack

Install Elasticsearch (HTTPS enabled)

Install Logstash and configure pipeline

Install Kibana and connect to Elasticsearch

4. Start Services
sudo systemctl start prometheus
sudo systemctl start grafana-server
sudo systemctl start elasticsearch
sudo systemctl start logstash
sudo systemctl start kibana
🧪 Log Testing

Generate logs:

logger "KCity Mall Alert: Payment Failure"

Check logs in Kibana → Discover

🚨 Alert Example
- alert: HighCPUUsage
  expr: avg(rate(node_cpu_seconds_total{mode="idle"}[5m])) < 0.2
  for: 1m
📸 Screenshots

(Add screenshots here)

Grafana Dashboard

Kibana Logs View

🎯 Outcome

This project demonstrates:

End-to-end observability setup

Real-time monitoring + logging integration
