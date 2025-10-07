# OTEL network policy ports issue

* https://issues.redhat.com/browse/TRACING-5670


Note that the operator does not correctly parse the `service.telemetry.metrics.readers` port. It is always set to `8888`.
The bug is reported here https://github.com/open-telemetry/opentelemetry-operator/issues/4233