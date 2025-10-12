# Docker Compose Project

## 📋 Prerequisites

- You should have a good understanding of Docker and its various commands.
- You should be proficient in using the Linux command-line interface.

## 🚀 Setting up

### 1.clone the repository
```bash
git clone <https://github.com/Maryam-bigdeli/docker-compose>
cd <docker-compose>
```

### 2. Before proceeding to the next section
```bash
docker --version
```
```bash
docker compose version
```

### 3.  Configuring Docker Compose
This project includes three main services that communicate through a shared network:

### 1. Frontend
- **Build**: Built from Dockerfile in the `frontend/` directory
- **Port**: `5173:80` (container port 80 mapped to host port 5173)
- **Depends on**: `backend` service
- **Network**: Uses `my-network` for communication

### 2. Backend
- **Build**: Built from Dockerfile in the `backend/` directory
- **Port**: `3000:3000`
- **Depends on**: `database` service
- **Network**: Uses `my-network` for communication

### 3. Database (MongoDB)
- **Image**: Uses official MongoDB image
- **Volume**: `mongodb_data` mounted to `/data/db` in the container
- **Network**: Uses `my-network` for communication
- **Storage**: Data is persistently stored in volume

### Network & Volume
- **Network**: `my-network` - Custom network for inter-service communication
- **Volume**: `mongodb_data` - For persistent database storage


##   Building and Running Services with Docker Compose

With your `docker-compose.yml` file ready, it's time to build and run your services using Docker Compose.

Execute the following command:
```bash
docker compose up
```

## 🛠️ Commands

| Command | Description |
|----------|-------------|
| `docker compose up` | Run all services |
| `docker compose up -d` | Run in detached mode (background) |
| `docker compose down` | Stop and remove containers |
| `docker compose ps` | List running services |
| `docker compose logs -f` | Follow logs in real-time |
| `docker compose restart` | Restart all services |
| `docker compose build` | Rebuild images |


## ⚙️ Configuration

### 🌿 Environment Variables
Environment variables are defined in the `docker-compose.yml` file or in a separate `.env` file.

---

### 🔌 Ports
- Main service: `http://localhost:3000`
- Database: `localhost:5432` (if available)

---

## 📚 Resources
- [Docker Documentation](https://betterstack.com/community/guides/scaling-docker/docker-compose-getting-started/ocs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)


