# Generic Helm Chart Template

A flexible Helm chart template for deploying applications on Kubernetes.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+

## Installation

```bash
# Install the chart
helm install my-release .

# Install with custom values
helm install my-release . -f values.yaml
```

## Configuration

The following table lists the configurable parameters and their default values.

| Parameter | Description | Default |
|-----------|-------------|----------|
| `replicaCount` | Number of replicas | `2` |
| `strategy.type` | Deployment strategy type (RollingUpdate or Recreate) | `RollingUpdate` |
| `strategy.rollingUpdate.maxSurge` | Maximum number of pods that can be created over the desired number | `1` |
| `strategy.rollingUpdate.maxUnavailable` | Maximum number of pods that can be unavailable during update | `0` |
| `revisionHistoryLimit` | Number of old ReplicaSets to retain for rollback | `3` |
| `image.repository` | Container image repository | `nginx` |
| `image.tag` | Container image tag | `latest` |
| `service.type` | Kubernetes service type | `ClusterIP` |
| `service.port` | Service port | `80` |
| `ingress.enabled` | Enable ingress | `false` |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install` or provide a values.yaml file:

```bash
helm install my-release . --set replicaCount=2
```