
## Run

wget https://github.com/open-telemetry/opentelemetry-collector-releases/releases/download/v0.131.1/otelcol-contrib_0.131.1_linux_amd64.tar.gz

```bash
otelcol-contrib --config collector.yaml
```

## Resources
* https://wiki.archlinux.org/title/Systemd/Journal
* https://opentelemetry.io/docs/specs/otel/logs/data-model/#field-severitytext
* https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/journaldreceiver#multiple-filtering-options
* https://github.com/open-telemetry/opentelemetry-collector-contrib/issues/7298#issuecomment-2186552440