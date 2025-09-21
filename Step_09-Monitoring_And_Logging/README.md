#  📊 Monitoring and Logging – Prometheus & Grafana

Monitoring and logging are essential parts of any production-grade DevOps workflow. They allow you to observe application performance, detect issues, and troubleshoot problems in real time. This setup uses Prometheus for metrics collection and Grafana for visualization.

---

## 📌 Why Monitoring & Logging?

- Provides real-time insights into application and infrastructure health.

- Enables alerting on anomalies or failures.

- Helps optimize performance and resource usage.

- Improves incident response and troubleshooting.

## 🚀 Implementation
### 1. Prometheus Setup

Prometheus collects metrics from your application or services.

Docker Compose example:
```yaml
version: "3.8"
services:
  prometheus:
    image: prom/prometheus:latest
    ports:
      - "9090:9090"
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml
```

prometheus.yml example:
```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'myapp'
    static_configs:
      - targets: ['myapp:3000']
```

- scrape_interval: how often Prometheus collects metrics

- targets: the services or apps that expose metrics endpoints

### 2. Grafana Setup

Grafana is used to visualize Prometheus metrics.

Docker Compose example:
```yaml
version: "3.8"
services:
  grafana:
    image: grafana/grafana:latest
    ports:
      - "3000:3000"
    environment:
      - GF_SECURITY_ADMIN_USER=admin
      - GF_SECURITY_ADMIN_PASSWORD=admin
```

- Default login: admin/admin

- Add Prometheus as a data source in Grafana via http://prometheus:9090.

### 3. Application Metrics

Your app must expose metrics for Prometheus. Example in Node.js using prom-client:
```js
const express = require('express');
const client = require('prom-client');

const app = express();
const collectDefaultMetrics = client.collectDefaultMetrics;
collectDefaultMetrics({ timeout: 5000 });

app.get('/metrics', async (req, res) => {
  res.set('Content-Type', client.register.contentType);
  res.end(await client.register.metrics());
});

app.listen(3000, () => console.log('Metrics available on /metrics'));
```

- Prometheus scrapes /metrics to collect CPU, memory, and custom application metrics.

### 4. Dashboards & Visualization

1. In Grafana, create a new Dashboard.

2. Add a Graph Panel, select Prometheus as the data source.

3. Example queries:
```text
# CPU usage for a container
rate(container_cpu_usage_seconds_total[1m])

# Memory usage
container_memory_usage_bytes
```

4. Save and share dashboards for team monitoring.

### 5. Alerts

Prometheus can trigger alerts when metrics cross thresholds. Example:
```yaml
groups:
  - name: myapp_alerts
    rules:
      - alert: HighCPUUsage
        expr: rate(container_cpu_usage_seconds_total[1m]) > 0.8
        for: 2m
        labels:
          severity: critical
        annotations:
          summary: "High CPU usage detected"
```

- Alerts can be sent to email, Slack, or other channels via Alertmanager.

✅ Verification

- Access Grafana at http://localhost:3000 and verify dashboards.

- Access Prometheus at http://localhost:9090/targets to verify targets are scraped.

Confirm application metrics appear on Grafana graphs.
