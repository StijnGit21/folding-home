# Folding@Home Docker Setup

This project sets up [Folding@Home](https://foldingathome.org/) using Docker Compose for easy deployment and management.

## About Folding@Home

Folding@Home is a distributed computing project that simulates protein folding and other molecular dynamics to help research diseases like cancer, COVID-19, Alzheimer's, and more.

## Prerequisites

- Docker and Docker Compose installed on your system
- Docker Compose v1.29+ or Docker with integrated Compose v2+

## Setup

### 1. Clone the repository

```bash
git clone <repository-url>
cd folding@home
```

### 2. Configure environment variables

Copy the `example.env` file to `.env` and update it with your settings:

```bash
cp example.env .env
```

Edit `.env` and fill in:
- `ACCOUNT_TOKEN`: Your Folding@Home account token (optional, but recommended for stats tracking)
- `MACHINE_NAME`: A friendly name for your machine on the Folding@Home network

### 3. Adjust paths and settings

Edit `docker-compose.yml` if needed:
- Replace `/path/to/foldingathome/data` with your desired data directory path
- Adjust volume mounts to fit your system
- Modify timezone if different from `Etc/UTC`

## Running

### Start the service

```bash
docker-compose up -d --build
```

### View logs

```bash
docker-compose logs -f foldingathome
```

### Stop the service

```bash
docker-compose down
```

### Restart the service

```bash
docker-compose restart foldingathome
```

## Configuration

### Environment Variables

- `PUID`: User ID for the container (default: 1000)
- `PGID`: Group ID for the container (default: 1000)
- `TZ`: Timezone setting (default: Etc/UTC)
- `ACCOUNT_TOKEN`: Your Folding@Home account token for stats tracking
- `MACHINE_NAME`: Display name for your Folding@Home machine

### Ports

- `7396`: Folding@Home control port (optional)

## Volumes

- `/config`: Main data directory for Folding@Home work units and configuration

## Resources

- [Folding@Home Official Site](https://foldingathome.org/)
- [Linux Server - Folding@Home Docker Image](https://hub.docker.com/r/linuxserver/foldingathome)
- [How to Join Folding@Home](https://foldingathome.org/start-folding/)

## License

See LICENSE file for details.
