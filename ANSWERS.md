# HW4 — Short Answers

Answer each question in 2–3 sentences.

## 1. Rolling-update safety
Why does the Deployment use `maxUnavailable: 0`, and what would change if it were `maxUnavailable: 1`?

> Using `maxUnavailable: 0` guarantees that Kubernetes never removes an existing pod until a replacement pod is healthy and ready to receive traffic. If `maxUnavailable` were set to `1`, one pod could be unavailable during the update, reducing capacity and increasing the chance of slower responses or dropped requests under heavy load.


## 2. Health probes
Why do the liveness/readiness probes target `/health` instead of `/predict`?

> The health probes use `/health` because it is a lightweight endpoint that simply verifies the application is running. Using `/predict` would unnecessarily execute the fraud model and depend on application logic or external services, making readiness and liveness checks slower and less reliable.

