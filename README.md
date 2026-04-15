# Running-N8n-locally
Guide on how to run N8n
To start n8n on Docker locally. Here are the steps:

**Quick Start with Docker:**

1. **Using Docker run command:**
```bash
docker run -it --rm --name n8n -p 5678:5678 n8n
```

This will:
- Download the latest n8n image
- Run n8n in interactive mode
- Map port 5678 to your machine
- Remove the container when stopped

2. **Access n8n:**
   - Open your browser to `http://localhost:5678`

**With Persistent Data (Recommended):**

If you want to keep your workflows after stopping the container:

```bash
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n n8n
```

This uses a Docker volume to persist your data.

**Using Docker Compose (Best for long-term use):**

Create a `docker-compose.yml` file:

```yaml
version: '3.8'

services:
  n8n:
    image: n8nio/n8n
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=password
    volumes:
      - n8n_data:/home/node/.n8n
    restart: unless-stopped

volumes:
  n8n_data:
```

Then run:
```bash
docker-compose up -d
```

**Requirements:**
- Docker installed and running
- Port 5678 available

Would you like me to help you set up Docker Compose or troubleshoot any issues?
