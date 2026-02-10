# ADR-001: Edge-First ML Deployment

## Status: Accepted | Date: 2026-02-10

## Decision
Deploy models as ONNX on CPU rather than cloud GPU inference.

## Why
- Cloud GPU = R5-50/hour ongoing cost
- ONNX on CPU = free after initial training
- Edge deployment = lower latency, works offline
- Most business ML models (classification, NLP, tabular) don't need GPU
- Training on cloud (one-time), inference on edge (ongoing)
