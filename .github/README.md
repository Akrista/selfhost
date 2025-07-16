# Akrista's Selfhost Vault

A curated collection of configurations for self-hosting various services, designed as a guide to experiment with best practices and deploy production-ready services with caution.

--------------------------------------------------

## Table of Contents

- [Overview](#overview)
- [Practices Followed](#practices-followed)
- [Usage Example](#usage-example)
- [Contributing](#contributing)

--------------------------------------------------

## Overview

This repository holds my personal collection of configuration files for self-hosting a variety of services. Although I try to follow industry best practices, please note that this guide is intended for personal learning and experimentation rather than as a foolproof production deployment manual.

Feel free to explore, experiment, and contribute by submitting [Pull Requests](https://github.com/akrista/selfhost/pulls).

--------------------------------------------------

## Practices Followed

This repository aims to adhere to the following best practices:

- **Descriptive Container Names**  
  Containers are given descriptive and unique names to simplify debugging and maintenance.

- **Use of Environment Variables**  
  Environment variables are used for dynamic configuration, making it easier to manage sensitive data and configurations across different environments.

- **Health Checks**  
  Implementing health checks helps in ensuring the availability and readiness of services.

- **Timezone Configuration**  
  Each service is configured with its preferred timezone where applicable, ensuring time consistency across logs and operations.

- **Automatic Updates with Watchtower**  
  Integration with Watchtower for automatic container updates is leveraged where possible to maintain the latest versions without manual intervention.

- **Port Commenting**  
  Unused ports are commented out in the configuration to avoid unintended exposures.

- **Network Segmentation**  
  Whenever possible, containers are separated into different networks (e.g., proxy, database, services) to enhance security and isolation.

--------------------------------------------------

## Usage Example

Below is an example snippet for deploying one of the services:

```yml
networks:
  default:
    name: services
    external: true
services:
  my_service:
    image: my_service_image:latest
    container_name: my_service_container
    restart: unless-stopped
    # Uncomment the port below only if needed
    # ports:
    #   - "8080:8080"
    environment:
      ENV_VAR: ${ENV_VAR}
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:8080"]
      interval: 30s
      timeout: 10s
      retries: 3
```

--------------------------------------------------

## Contributing

To contribute:

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/my-feature`).
3. Commit your changes (`git commit -m 'Add my feature'`).
4. Push to the branch (`git push origin feature/my-feature`).
5. Open a Pull Request detailing your changes.

Please ensure your code follows the repository's style and that you include clear commit messages.
