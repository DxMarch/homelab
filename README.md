# My Homelab

This project sets up Headscale with a web UI and Traefik reverse proxy using Docker Compose.

## Prerequisites

- Docker and Docker Compose installed
- A domain name pointing to your server
- Ports 80 and 443 open/forwarded to your server

## Quick Start

1. Clone the repo:
```bash
git clone https://github.com/DxMarch/homelab.git
cd homelab
```

2. Replace placeholders with your actual values. Oon linux you can run:
```bash
# Replace email in Traefik's docker-compose.yml
sed -i "s|__LE_EMAIL__|<your_email>|g" ./traefik/compose.yml

# Replace domain in Headscale's docker compose
sed -i "s|__HEADSCALE_DOMAIN__|<your_domain>|g" ./headscale/compose.yml

# Replace domain in Headscale's config
sed -i "s|__HEADSCALE_DOMAIN__|<your_domain>|g" ./headscale/config.yaml
```

3. Start the services:
```bash
# Start Traefik first (creates the network)
docker compose -f ./traefik/compose.yaml up -d

# Then start Headscale
docker compose -f ./headscale/compose.yaml up -d
```

## Sources
- [Headscale with UI in Docker](https://www.youtube.com/watch?v=DI4JFrBOBZs)