# ML Pipeline

> End-to-end ML ops — feature store, model versioning, A/B testing, drift detection, automated retraining. Designed for edge deployment on modest hardware (CPU-only, no GPU required).

[![Python](https://img.shields.io/badge/python-3.10+-blue)]()
[![scikit-learn](https://img.shields.io/badge/sklearn-models-orange)]()
[![ONNX](https://img.shields.io/badge/ONNX-edge_deploy-green)]()
[![DVC](https://img.shields.io/badge/DVC-versioning-purple)]()

## Pipeline

```
Raw Data ──▶ Feature Store ──▶ Training ──▶ Model Registry
                (SQLite/          │           (DVC)
                 Parquet)         │              │
                                  ▼              ▼
                            ┌──────────┐  ┌──────────┐
                            │ Evaluate │  │   A/B    │
                            │ (metrics)│  │  Testing │
                            └────┬─────┘  └────┬─────┘
                                 │              │
                                 ▼              ▼
                            ┌──────────┐  ┌──────────┐
                            │  Deploy  │  │  Monitor │
                            │  (ONNX)  │  │  (drift) │
                            └──────────┘  └────┬─────┘
                                               │ drift detected
                                               ▼
                                          ┌──────────┐
                                          │ Retrain  │ ← automated trigger
                                          └──────────┘
```

## Features

| Feature | Description |
|---------|-------------|
| Feature store | SQLite/Parquet-based, versioned features |
| Model registry | DVC-tracked model artifacts with metadata |
| A/B testing | Traffic splitting with statistical significance |
| Drift detection | KS test + PSI for data/concept drift |
| Auto-retraining | Trigger retraining when drift exceeds threshold |
| Edge deployment | ONNX export for CPU-only inference |
| Experiment tracking | MLflow-compatible logging |

## Hardware Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| CPU | 2 cores | 4 cores |
| RAM | 4GB | 8GB |
| GPU | Not required | Not required |
| Disk | 10GB | 50GB |

Runs on an i7-6500U with 8GB RAM. No cloud GPU needed.

## Revenue

ML consulting **R800/hour**. Model deployment **R5,000-10,000 per model**. Ongoing monitoring **R2,000/month**. "We deploy AI that runs on YOUR hardware, not rented GPUs."

---
*MIT License*
