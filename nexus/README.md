# Local Nexus registry setup

# Intro
For startup Nexus registry you will need to increase in Docker settings RAM to up to 4 GB. Otherwise you will not be able to start the service. It will crash with 137 error

## Docker-compose content 
We will use http://localhost:8081 for access to Nexus web interface and http://localhost:8123 for Docker-registry

```yaml
version: "3"

services:
    nexus:
        image: sonatype/nexus3:latest
        ports:
            - "8081:8081"
            - "8123:8123"
        volumes:
            - ./data:/nexus-data
