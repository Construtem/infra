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
- Configurar los .env con los datos segun se indican en el .env.example de cada repo
- Pedirme a mí (Andres) las variables de entorno si desean levantar todos los servicios +56979828311

### 3. Levantar los servicios
- Antes de levantar los servicios debes situarte en la terminal, en el directorio infra y actualizar los repos con:
```bash
git pull origin main
``` 
- Luego para levantar los servicios, dentro del mismo directorio que hiciste "git pull" debes hacer:
```bash
docker compose up --build
```
- Luego de ejecutar el comando, se levantaran todos los servicios en tu pc y los tendrás disponibles en sus respectivos puertos del localhost
  
## 🔄 Actualizar submódulos a la rama develop
### ✅ Pasos para actualizar un submódulo

### 1.- Ir al submodulo que deseas actualizar:
```bash
cd frontend-ventas
```
### 2.- Cambiar a la rama develop y traer los últimos cambios:
```bash
git switch develop
```
```bash
git pull origin develop
```
### 3.- Volver al directorio raiz de infra:
```bash
cd ..
```
### ✅ Ahora puedes levantar con docker compose up --build asegurándote que están todos los repos actualizados ;)
