# Despliegue y entorno

## Requisitos previos

- Git
- Docker Engine y Docker Compose v2
- Node.js 22 (solo si se usa el entorno local fuera de contenedores)
- Java 25 (solo si se usa el entorno local fuera de contenedores)

## Preparación del entorno

1. Clona este repositorio
2. Crea un archivo `.env` desde `.env.example`
3. Revisa las variables específicas de cada servicio
4. Ejecuta la preparación del proyecto para clonar los repos dependientes

```bash
./prepareEnviroment.sh
```

En Windows puedes usar:

```powershell
./prepareEnviroment.ps1
```

## Arranque en desarrollo

```bash
docker compose -f docker-compose.dev.yml up --build
```

## Arranque en producción local

```bash
docker compose up --build -d
```

## Verificación rápida

- Frontend: http://localhost:4200
- Middle server: http://localhost:3000
- DB server: http://localhost:8080
- Nginx: http://localhost o https://localhost
- MinIO: http://localhost:9000 y http://localhost:9001
- PostgreSQL: localhost:5432 (solo local)
- MongoDB: localhost:27017 (solo local)
- Redis: localhost:6379 (solo local)

## Buenas prácticas

- No publiques credenciales reales ni `.env` en GitHub
- Comprueba los logs si falla un servicio concreto
- Usa `docker compose down -v` solo si quieres limpiar volúmenes persistentes
- Si cambias puertos, variables o servicios, actualiza la documentación

## Recuperación ante fallos

Cuando un servicio falle:

```bash
docker compose logs -f <servicio>
```

Si el problema es de infraestructura o arranque, revisa primero:

- variables de entorno
- puertos ocupados
- dependencias y orden de arranque
- cambios en Docker Compose o nginx
