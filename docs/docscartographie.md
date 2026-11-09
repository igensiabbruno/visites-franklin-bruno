# Cartographie du service Visites (Atelier A1)

## 1. Vue d'ensemble

Le service `visites` est une API REST légère conçue pour mesurer et exposer la fréquence des consultations web, tout en offrant une interface de monitoring native pour Prometheus.

```text
       [ Client Web / cURL ]
                 │
                 ▼ (HTTP :8000)
    ┌───────────────────────────┐
    │       FastAPI (App)       │
    │  ├─ GET  / (incrément)    │
    │  ├─ POST /reset           │
    │  ├─ GET  /health          │
    │  └─ GET  /metrics         │
    └─────────────┬─────────────┘
                  │ (TCP :6379)
                  ▼
          ┌───────────────┐
          │ Redis Server  │
          │ (Clé: visites)│
          └───────────────┘
