# Useful-Docker-Commands

This document lists useful Docker commands for managing containers, images, volumes, and networks in your development or production environment.

---

## Containers

- **List all containers (running and stopped):**
  ```sh
  docker ps -a
  ```

- **Stop all running containers:**
  ```sh
  docker stop $(docker ps -q)
  ```

- **Remove all containers:**
  ```sh
  docker rm $(docker ps -aq)
  ```
  
- **Remove everything (volumes and containers):**
  ```sh
  docker rm -f $(docker ps -aq)
  docker volume rm $(docker volume ls -q)
  ```
---

## Images

- **List all images:**
  ```sh
  docker images
  ```

- **Remove all images:**
  ```sh
  docker rmi $(docker images -q)
  ```

---

## Volumes

- **List all volumes:**
  ```sh
  docker volume ls
  ```

- **Delete all unused volumes:**
  ```sh
  docker volume prune
  ```

- **Delete all Docker volumes used by containers:**
  ```sh
  docker volume rm $(docker volume ls -q)
  ```

---

## Networks

- **List all networks:**
  ```sh
  docker network ls
  ```

- **Remove all unused networks:**
  ```sh
  docker network prune
  ```

---

## System Cleanup

- **Remove all stopped containers, unused networks, dangling images, and build cache:**
  ```sh
  docker system prune
  ```

- **Remove everything (containers, images, volumes, networks):**
  ```sh
  docker system prune -a --volumes
  ```

---

## Compose

- **Start services defined in docker-compose.yml:**
  ```sh
  docker-compose up
  ```

- **Stop services:**
  ```sh
  docker-compose down
  ```

- **Rebuild services:**
  ```sh
  docker-compose up --build
  ```

---

> **Note:** Use these commands with caution, especially those that remove resources, as they may delete important data or running
