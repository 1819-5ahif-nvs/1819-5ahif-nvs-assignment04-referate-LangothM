# Docker

## How to start?

Installieren von docker und docker-compose, die Installation von docker-compose für Linux/MacOS/Windows ist hier nach zu lesen: https://docs.docker.com/compose/install/

Nach der Installation und dem klonen des Projekt müssen nur noch diese Befehle im Terminal eingegen werden:

```bash
cd docker_example
docker-compose up --build
```

Nun werden alle Docker Images vom dockerhub gepullt und anschließend gebaut. Schlussendlich läuft nach der Downloadphase ein Wildfly und eine MySQL-Db. Zugreifen kann man darauf ganz normal über 
http://localhost:8080 (Wildfly) & http://localhost:3306 (PHPMyAdmin für MySQL).

#### Näheres dazu im PDF!

