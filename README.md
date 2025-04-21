# 🚀 Puente Trading Platform  

![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=FastAPI&logoColor=white) ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)  

Una plataforma de trading que muestra valores de acciones y criptomonedas en tiempo real, con autenticación de usuarios, favoritos y búsqueda avanzada.

## 🚀 Comenzando

### 📋 Requisitos previos

- Docker (para instalación con contenedores)
- Python 3.9+ y Node.js 16+ (para instalación manual)
- PostgreSQL (para instalación manual)

#### Linux (Debian/Ubuntu)

```bash
# Docker y docker-compose
sudo apt update
sudo apt install docker.io docker-compose -y
sudo systemctl enable docker
sudo systemctl start docker

# Python 3.9+
sudo apt install python3.9 python3.9-venv python3-pip -y

# Node.js 16+
sudo apt install -y nodejs

# PostgreSQL
sudo apt update
sudo apt install postgresql postgresql-contrib -y
sudo systemctl enable postgresql
sudo systemctl start postgresql
```

#### Windows

- **Docker:** [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- **Python 3.9+:** [Descargar Python](https://www.python.org/downloads/)
- **Node.js 16+:** [Descargar Node.js v22](https://nodejs.org/es)
- **PostgreSQL:** [Descargar PostgreSQL](https://www.postgresql.org/download/)

Verificá las versiones en PowerShell:

```powershell
python --version
node --version
docker --version
```
---

## 📦 Instalación con Docker (recomendado)
🛑 Aviso: El repositorio incluye dos submodulos, es necesario clonarlo con git clone --recurse-submodules o garantizar la descarga de ambos submodulos.

```bash
git clone --recurse-submodules git@github.com:braianowen/puente-trading-platform.git
cd puente-trading-platform
docker-compose build --no-cache
docker-compose up -d
```

🔍 Verificar estado de los contenedores:

```bash
docker-compose ps
```

🌐 Acceder a la aplicación:

- **Frontend**: [http://localhost:3000](http://localhost:3000)  
- **API Docs**: [http://localhost:8000/docs](http://localhost:8000/docs)

👑 Promover usuario a administrador:

```bash
docker-compose run --rm backend python promote_to_admin.py nombre_usuario
```

🛑 Detener servicios (⚠️ borra la base de datos):

```bash
docker-compose down
```

## 👀 ¿Cómo ver la aplicación?

  - Accedé a http://localhost:3000 para ver la página principal. La plataforma incluye:

  - 📈 Visualización en tiempo real de valores de acciones y criptomonedas.

  - 🔐 Registro y login de usuarios con autenticación segura vía JWT.

  - ⭐ Sistema de favoritos para guardar tus instrumentos preferidos.

  - 🔎 Buscador para filtrar rápidamente acciones y monedas.

  - 📟 Modal informativo con datos históricos al seleccionar una acción o moneda.

  - 🔌 Servicios backend que consultan Alpha Vantage y CoinGecko para obtener valores actualizados.

  - 🧠 Manejo de estado global (store) para instrumentos y favoritos.

---

## 🛠 Instalación Manual

### 🐧 Linux

```bash
# Configurar la base de datos
sudo -u postgres psql -c "ALTER USER admin WITH PASSWORD 'password';"
sudo -u postgres psql -c "CREATE DATABASE mydb;"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE mydb TO admin;"
```

```bash
# Backend
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 dev-tables.py
uvicorn main:app --reload --port 8000
```

```bash
# Frontend (en otra terminal)
cd ../frontend
npm install
npm run dev
```

### 🪟 Windows (PowerShell)

```sql
-- Configurar la base de datos
ALTER USER admin WITH PASSWORD 'password';
CREATE DATABASE mydb;
GRANT ALL PRIVILEGES ON DATABASE mydb TO admin;
```

```powershell
# Backend
cd backend
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
python dev-tables.py
uvicorn main:app --reload --port 8000
```

```powershell
# Frontend (en otra terminal)
cd ../frontend
npm install
npm run dev
```

---

## 📚 Documentación

- API Swagger: [http://localhost:8000/docs](http://localhost:8000/docs)
- Colección Postman: `backend/docs/Puente-trading-platform.postman_collection.json`

---

## ✨ Características

- ✅ Autenticación JWT segura
- ⭐ Sistema de favoritos
- 🔍 Búsqueda en tiempo real
- 🛠 Panel administrativo
- 📄 Documentación Swagger/OpenAPI
- 🐳 Dockerizado para fácil despliegue

---

## 📜 Licencia

MIT © [Braian Owen](https://github.com/braianowen)

---

## 🙋‍♂️ ¿Problemas?

Abre un issue en GitHub

## 🚀 ¿Quieres contribuir?

Envía un Pull Request