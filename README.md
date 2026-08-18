# Helm charts

This repository keeps independently versioned Helm charts under `charts/`.

## Layout

```text
helm-charts/
├── .github/workflows/
│   ├── ci.yaml
│   └── release-duynh-oci.yaml
├── charts/
│   └── duynh/
│       ├── Chart.yaml
│       ├── values.yaml
│       ├── values.schema.json
│       ├── templates/
│       ├── tests/
│       ├── examples/
│       └── README.md
├── .gitignore
└── README.md
```

## Add another chart

Create it under `charts/`, then add its path to the `chart` matrix in `.github/workflows/ci.yaml`:

```bash
helm create charts/payments
```

Each chart keeps its own `Chart.yaml` version and should have a chart-specific OCI release workflow and tag prefix, for example `payments-v0.1.0`.

See [`charts/duynh/README.md`](charts/duynh/README.md) for installation, testing, Envoy Gateway, and OCI usage.
