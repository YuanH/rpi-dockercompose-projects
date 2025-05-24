# Grafana Monitoring Stack

This project sets up a complete monitoring solution using Grafana, Prometheus, and Node Exporter on a Raspberry Pi.

## Components

- **Grafana**: Visualization and analytics platform
- **Prometheus**: Time series database for metrics collection
- **Node Exporter**: System metrics exporter for hardware and OS stats

## Prerequisites

- Docker and Docker Compose installed
- External Docker network named `shared-network`
- Sufficient disk space for persistence volumes

## Directory Structure
```
grafana-stack/
├── docker-compose.yml
├── prometheus.yml
├── prometheus_data/
├── grafana_data/
└── grafana_config/
```

## Configuration

### Volume Paths
The stack uses local bind mounts at:
- `/home/yuan/repo/grafana-stack/prometheus_data`
- `/home/yuan/repo/grafana-stack/grafana_data`
- `/home/yuan/repo/grafana-stack/grafana_config`

### Default Ports
- Grafana: 3000
- Prometheus: 9090
- Node Exporter: 9100

### Default Credentials
- Grafana:
  - Username: admin
  - Password: admin

## Usage

Start the stack:
```bash
docker-compose up -d
```

### Network Configuration
Uses the `shared-network` for integration with other services like Cloudflare Tunnel.
