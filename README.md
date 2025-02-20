# WordPress Docker Compose Setup

This repository contains a Docker Compose configuration for running WordPress with MySQL.

## Prerequisites

- Docker Engine installed
- Docker Compose installed

## Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/DjeridiY/wordpress-docker-compose-demo.git
   cd wordpress-docker-compose-demo
   ```

2. Start the containers:
   ```bash
   docker-compose up -d
   ```

3. Access WordPress:
   - Open your browser and navigate to `http://localhost:8080`
   - Follow the WordPress installation wizard

## Configuration

The setup includes:
- WordPress (latest version)
- MySQL 8.0
- Persistent volumes for both WordPress and MySQL data
- Custom network for container communication

### Default Credentials

MySQL Database:
- Database: `wordpress`
- User: `wordpress_user`
- Password: `wordpress_password`
- Root Password: `root_password`

**Note:** For production use, please change these default credentials in the `docker-compose.yml` file.

## Stopping the Services

To stop the containers:
```bash
docker-compose down
```

To stop the containers and remove all data (volumes):
```bash
docker-compose down -v
```

## Maintenance

- WordPress files are stored in the `wordpress_data` volume
- MySQL data is stored in the `db_data` volume
- Both services will automatically restart if they crash

## Security Notes

For production deployment:
1. Change all default passwords in `docker-compose.yml`
2. Consider using Docker secrets for sensitive data
3. Set up SSL/TLS for secure connections
4. Configure proper backup strategies