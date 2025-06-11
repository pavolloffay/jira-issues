
## Generate data

```bash
kubectl port-forward -n tracing-system svc/dev-collector 4318:4318 
docker run --rm -it --net=host ghcr.io/open-telemetry/opentelemetry-collector-contrib/telemetrygen:latest traces --otlp-http=true --otlp-insecure --otlp-endpoint localhost:4318 --child-spans=2 --workers=3  --traces=1000
```