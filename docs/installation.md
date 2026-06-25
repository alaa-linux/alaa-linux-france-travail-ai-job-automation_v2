# Installation — Job Automation Assistant V2

## 1. Préparer Ubuntu

```bash
sudo apt update

sudo apt install -y \
curl \
wget \
zip \
unzip \
tree \
docker.io \
docker-compose \
postgresql
```

---

## 2. Vérifier Docker

```bash
docker --version

docker-compose --version

docker ps
```

---

## 3. Installer Ollama

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

---

## 4. Télécharger les modèles IA

### Analyse offres

```bash
ollama pull gemma3:1b
```

### Génération LM

```bash
ollama pull phi4
```

---

## 5. Vérifier Ollama

```bash
ollama list
```

---

## 6. Lancer PostgreSQL

```bash
sudo systemctl start postgresql

sudo systemctl status postgresql
```

---

## 7. Connexion PostgreSQL

```bash
sudo -u postgres psql
```

---

## 8. Base projet

```sql
CREATE DATABASE jobdb;
```

Connexion :

```sql
\c jobdb
```

---

## 9. Lancer n8n

Depuis le dossier projet :

```bash
docker compose up -d
```

---

## 10. Vérifier n8n

```bash
docker ps
```

Accès :

```text
http://localhost:5678
```

---

## 11. Vérifier workflow

```text
Workflow actif
Connexion PostgreSQL OK
Connexion Ollama OK
Connexion SMTP OK
```
