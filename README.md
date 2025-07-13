# 🛠️ Construtem Infraestructura

Este repositorio contiene la infraestructura central del proyecto **Construtem**, permitiendo levantar todos los microservicios (frontend y backend) de forma automática utilizando `docker-compose`.

## 📦 Servicios incluidos

- `front-login`--> localhost:3000
- `front-inventario`--> localhost:3001
- `front-ventas`--> localhost:3002
- `front-facturacion`--> localhost:3003
- `back-login`--> localhost:8080
- `back-inventario`--> localhost:8081
- `back-ventas`--> localhost:8082
- `back-facturacion`--> localhost:8083

Todos los servicios son incluidos como **submódulos Git**, apuntando a sus respectivos repositorios.

---

## 🚀 Instalación

### 1. Clonar el repositorio con submódulos

```bash
git clone --recurse-submodules https://github.com/Construtem/infra.git
cd infra
```
### 2. Configurar variables de entorno

- Crear en cada repo de backend un archivo .env
- Crear en cada repo de frontend un archivo .env.local
- Configurar los .env y .env.local los datos segun se indican en el .env.example de cada repo

### 3. Levantar los servicios

```bash
docker compose up --build
```
