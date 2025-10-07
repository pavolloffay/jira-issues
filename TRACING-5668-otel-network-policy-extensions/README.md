# OTEL network policy ports extensions issue

* https://issues.redhat.com/browse/TRACING-5686


Note that the operator does not correctly parse the `service.telemetry.metrics.readers` port. It is always set to `8888`.
The bug is reported here https://github.com/open-telemetry/opentelemetry-operator/issues/4233


## Notes

* Only `health_check`, `jaeger_query` and `k8s_observer` extensions are parsed by the operator https://github.com/open-telemetry/opentelemetry-operator/blob/main/internal/components/extensions/helpers.go#L14
* Only ports from these extensions are added the `pod`, `service` and `networkpolicy` objects.


### Workaround

Expose ports directly in the collector CR: 

```yaml
spec:
  ports:
    - name: jaeger-sampling
      appProtocol: grpc
      port: 14250
      protocol: TCP
      targetPort: 14250
```