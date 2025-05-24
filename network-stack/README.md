# Network Stack

This project sets up a secure networking infrastructure using Cloudflare Tunnel and Tailscale on a Raspberry Pi.

## Components

- **Cloudflare Tunnel**: Secure external access without opening ports
- **Tailscale**: Zero-config VPN for secure internal access

## Prerequisites

- Docker and Docker Compose installed
- Cloudflare account and tunnel token
- Tailscale account and auth key
- External Docker network named `shared-network`

## Configuration

### Environment Variables
Create a `.env` file with:
```
CLOUDFLARE_TUNNEL_TOKEN=your-tunnel-token
TS_AUTH_KEY=your-tailscale-auth-key
```

### Directory Structure
```
network-stack/
├── docker-compose.yml
├── .env
├── .cloudflared/
│   └── config.yml
└── tailscale-data/
```

## Usage

Start the stack:
```bash
docker-compose up -d
```

### Cloudflare Tunnel
- Automatically establishes secure tunnel
- Configure hostnames in `.cloudflared/config.yml`

### Tailscale
- Auto-connects to your Tailscale network
- Uses host networking mode
- Device name: docker-pi

## Network Configuration
Uses an external Docker network `shared-network` for communication between containers and other stacks.
