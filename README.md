# Continuum QA

This repository orchestrates the Quality Assurance environment for the Continuum platform.

## Overview

The QA environment is built using the latest Docker images from the [Frontend](../continuum-frontend) and [Backend](../continuum-backend) repositories.

Images are automatically built and pushed to GHCR (GitHub Container Registry) by their respective CI workflows.

## Environment Stack

- **Backend:** FastAPI (Python 3.12)
- **Frontend:** React (Vite)
- **Database:** PostgreSQL 16
- **Mail:** Mailpit (SMTP testing)

## How to Deploy

The deployment is managed via GitHub Actions.

1.  Go to the **Actions** tab in this repository.
2.  Select the **Deploy QA Environment** workflow.
3.  Click **Run workflow**.

This will pull the latest `:latest` tags from GHCR and restart the services.

## Local Setup (Optional)

If you want to run the QA stack locally:

```bash
# Login to GHCR
echo $GITHUB_TOKEN | docker login ghcr.io -u YOUR_USERNAME --password-stdin

# Pull and run
docker compose pull
docker compose up -d
```

---

## Service URLs (Default)

- **Frontend:** http://localhost:5174
- **Backend API:** http://localhost:8001/api
- **API Docs:** http://localhost:8001/docs
- **Mailpit UI:** http://localhost:8025
