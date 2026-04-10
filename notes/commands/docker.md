# Docker Quickref

Use with: `qref docker`

## Core Commands

| Task | Command |
|---|---|
| List images | `docker images` |
| List running containers | `docker ps` |
| List all containers | `docker ps -a` |
| Build image | `docker build -t app:tag .` |
| Run container | `docker run -d --name app -p 8080:80 app:tag` |
| Logs (follow) | `docker logs -f app` |
| Shell into container | `docker exec -it app sh` |
| Stop container | `docker stop app` |
| Remove container | `docker rm app` |
| Remove image | `docker rmi app:tag` |

## Compose

- `docker compose up -d`
- `docker compose ps`
- `docker compose logs -f`
- `docker compose exec app sh`
- `docker compose down`

## Cleanup

- `docker container prune`
- `docker image prune`
- `docker volume prune`
- `docker system prune`
- `docker system prune -a --volumes`

## Common Flow

```bash
docker build -t myapp:dev .
docker run --name myapp -p 8080:8080 myapp:dev
docker logs -f myapp
docker exec -it myapp sh
docker stop myapp && docker rm myapp
```
