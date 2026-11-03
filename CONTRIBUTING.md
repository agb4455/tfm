# Guía de contribución

Gracias por querer colaborar en Viking Clan Wars.

Este repositorio es el orquestador del proyecto y coordina el arranque del frontend, del middle server y del DB server. Antes de tocar código o infraestructura, conviene tener claro qué parte del sistema estás modificando.

## 1. Estructura del proyecto

- `front/`: frontend Angular
- `middle_server/`: motor del juego y API HTTP/Socket.IO
- `db_back/`: backend Java/Spring con persistencia y analítica
- `nginx/`: proxy inverso y configuración TLS
- `docker-compose*.yml`: composición del entorno
- `prepareEnviroment.*`: scripts de preparación del entorno

## 2. Cómo empezar

1. Haz un fork del repositorio o crea una rama desde `main`.
2. Clona el repositorio y prepara el entorno:

```bash
./prepareEnviroment.sh
```

3. Configura tus variables de entorno en un `.env` local.
4. Levanta el entorno con Docker Compose:

```bash
docker compose -f docker-compose.dev.yml up --build
```

## 3. Reglas básicas

- No subas secretos ni credenciales reales.
- No publiques archivos `.env` ni tokens.
- Mantén los cambios acotados a una funcionalidad o corrección.
- Si cambias infraestructura, revisa también el README y la documentación asociada.
- Si cambias la arquitectura de un servicio, actualiza los README y los scripts que dependan de ello.

## 4. Convenciones de ramas

Usa nombres descriptivos:

- `feature/nombre-funcionalidad`
- `fix/correccion-bug`
- `docs/mejora-readme`
- `refactor/clean-up-componente`

## 5. Convenciones de commits

Usa mensajes claros y cortos, preferiblemente en inglés o en español de forma coherente con el repositorio. Ejemplos:

- `feat: add matchmaking flow`
- `fix: resolve handshake validation bug`
- `docs: improve deployment guide`
- `refactor: simplify nginx config`

## 6. Pull requests

Antes de abrir un PR:

- Revisa que el entorno arranca con el proyecto completo.
- Ejecuta las pruebas relevantes del servicio que hayas tocado.
- Haz una descripción breve con:
  - qué cambia
  - por qué cambia
  - cómo probarlo
- Si el cambio afecta a varios repos, indica explícitamente qué repos están implicados.

## 7. Detección y validación

Si cambias algo de:
- Docker Compose o Nginx → valida la composición del entorno.
- Frontend → prueba el arranque del cliente y el flujo con el middle server.
- Middle server → prueba la API, sockets y integración con DB server.
- DB server → ejecuta los tests de Spring y revisa migraciones.

## 8. Documentación

Los cambios relevantes deben ir acompañados de:

- README actualizado si cambia la forma de ejecutar el proyecto
- comentarios de configuración si se añaden variables nuevas
- notas de despliegue si se altera infraestructura o puertos

## 9. Preguntas y ayuda

Si tienes dudas sobre arquitectura, publicación o flujo de trabajo, abre un issue con el contexto suficiente y detallando qué parte del proyecto te interesa.

Gracias por ayudar a mejorar Viking Clan Wars.
