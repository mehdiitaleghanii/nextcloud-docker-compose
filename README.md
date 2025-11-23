# Nextcloud Docker Setup

A Docker Compose setup for running Nextcloud with MariaDB and Redis.

## Services

- **Nextcloud**: Main application (port 80)
- **MariaDB**: Database server (ports 3306, 33060)
- **Redis**: Caching service

## Prerequisites

- Docker and Docker Compose installed
- Environment variables configured (see below)

## Environment Variables

Create a `.env` file in the project root with the following variables:

```env
MYSQL_ROOT_PASSWORD=root
MYSQL_PASSWORD=your_db_password
MYSQL_DATABASE=nextcloud
MYSQL_USER=nextcloud
```

## Quick Start

1. Create a `.env` file with the required environment variables
2. Start the services:

```bash
docker-compose up -d
```

3. Access Nextcloud at `http://localhost`

## Management

**Stop services:**
```bash
docker-compose down
```

**View logs:**
```bash
docker-compose logs -f
```

**Restart services:**
```bash
docker-compose restart
```

## Volumes

- `nextcloud`: Nextcloud application data
- `nextcloud-db`: MariaDB database data

## Notes

- MariaDB uses `READ-COMMITTED` transaction isolation level (recommended for Nextcloud)
- Redis is used for caching to improve performance
- Database credentials are shared between the app and db services


