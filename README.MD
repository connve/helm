# CONNVE Helm Charts

This repository contains Helm charts for deploying CONNVE services on Kubernetes.

## Usage

### Add the Helm repository

```bash
helm repo add connve https://connve-labs.github.io/helm
helm repo update
```

### Install a chart

```bash
# Example: Install flowgen
helm install my-flowgen connve/flowgen \
  --namespace flowgen \
  --create-namespace \
  -f values.yaml
```

### Install from local chart (for development)

```bash
# Example: Install flowgen from local chart
helm install my-flowgen ./charts/flowgen \
  --namespace flowgen \
  --create-namespace \
  -f values.yaml
```

## Available Charts

- **[flowgen](./charts/flowgen)**

## Configuration

Each chart has its own `values.yaml` file with configurable options. See the individual chart directories for details:

- [flowgen values](./charts/flowgen/values.yaml)

## Development

### Testing chart changes locally

```bash
# Lint a chart
helm lint charts/flowgen

# Dry-run template generation
helm template my-release charts/flowgen -f your-values.yaml

# Install locally for testing
helm install my-release charts/flowgen \
  --namespace flowgen \
  --create-namespace \
  --dry-run --debug
```

### Package a chart

```bash
helm package charts/flowgen
```

## Releases

Charts are automatically packaged and released to GitHub Pages when changes are pushed to the `main` branch.

The Helm repository is available at: `https://connve-labs.github.io/helm`