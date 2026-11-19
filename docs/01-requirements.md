# Requirements

## Functional
- FR1: Ingest the raw dataset, validate its schema, and produce a deterministic
  train/validation/test split.
- FR2: Train at least three candidate models (e.g. logistic regression,
  random forest, gradient boosting) as scikit-learn Pipelines.
- FR3: Log parameters, metrics and artifacts of every run to MLflow.
- FR4: Select the best candidate by a defined rule and register it as a new
  model version.
- FR5: Mark the promoted version with the `champion` alias.
- FR6: Serve predictions over HTTP from the registered champion.
- FR7: Expose `/health` and `/metrics` endpoints.
- FR8: Record request count, latency, errors and prediction distribution.

## Non-functional
- NFR1 Reproducibility: same code + data + params + seed = same metrics.
- NFR2 Latency: p95 of /predict under 100 ms on a single CPU container.
- NFR3 Startup: API ready within 10 s of container start.
- NFR4 Quality gates: lint, type check and tests pass before any merge.
- NFR5 Coverage: at least 80% on src/.
- NFR6 Security: no secrets in the repo; all config via environment variables.
- NFR7 Separation: serving code never imports training code.

## Out of scope
- Real-time retraining, feature store, Kubernetes, authentication,
  fairness certification.