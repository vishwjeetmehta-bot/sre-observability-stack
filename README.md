<div align="center">

# 📊 Enterprise SRE Observability Stack

[![Prometheus](https://img.shields.io/badge/Prometheus-v2.50-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)](https://prometheus.io/)
[![Grafana](https://img.shields.io/badge/Grafana-v10.4-F46800?style=for-the-badge&logo=grafana&logoColor=white)](https://grafana.com/)
[![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-Collector-495057?style=for-the-badge&logo=opentelemetry&logoColor=white)](https://opentelemetry.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](./LICENSE)

<p align="center">
  <b>Production-grade Site Reliability Engineering (SRE) observability suite with Prometheus error-budget alert rules, OpenTelemetry telemetry pipelines, and Grafana golden signal dashboards.</b>
</p>

</div>

---

## 📈 SRE Golden Signals & SLO Architecture

```
 Microservices / Pods (OTel SDK)
              │ Traces / Metrics (OTLP gRPC)
              ▼
┌─────────────────────────────────┐
│ OpenTelemetry Collector         │
│  - Batch processor              │
│  - Memory limiter               │
└─────────────┬───────────────────┘
              │ Exposes Prometheus Metrics
              ▼
┌─────────────────────────────────┐
│ Prometheus Enterprise Engine    │
│  - PromQL Burn-Rate Evaluator   │
└─────────────┬───────────────────┘
              │
       ┌──────┴──────────────────────┐
       ▼                             ▼
[ Grafana Dashboards ]      [ Alertmanager -> PagerDuty ]
 - 99.9% SLO Availability     - P1 Critical: Error Budget Burn > 2%
 - P99 Latency (ms)           - P2 Warning: Memory Pressure
```

---

## 📁 Repository Layout

```
sre-observability-stack/
├── .github/workflows/
│   └── ci.yml                     # Syntax and schema validation for rules & dashboards
├── prometheus/rules/
│   └── sre_alerts.yaml            # Multi-window error budget burn rate alerting
├── grafana/dashboards/
│   └── sre-slo-metrics.json       # Production executive SLI/SLO dashboard
├── otel-collector/
│   └── config.yaml                # Standardized OpenTelemetry collector pipeline
└── README.md
```

---

## 👤 Author

**Vishwjeet Kumar Mehta**  
Senior DevOps & DevSecOps Consultant | Cloud & Infrastructure Architect  
- **LinkedIn**: [linkedin.com/in/vishwjeetmehta](https://linkedin.com/in/vishwjeetmehta)  
- **GitHub**: [@vishwjeetmehta-bot](https://github.com/vishwjeetmehta-bot)
