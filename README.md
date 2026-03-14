# n8n Infra Sync

### Centralized Workflow Deployment

This repository stores the reusable GitHub action (`sync.yml`) used to securely map exported `*.json` workflows from remote project repositories up to a centralized n8n server instance hosted on Railway.

### Configuration
Ensure that your GitHub Organization or Personal Account is configured with the following Actions Secrets:
- `N8N_HOST`: The complete URL to the central n8n server (e.g. `https://your-n8n.up.railway.app`)
- `N8N_API_KEY`: The API key generated from the n8n dashboard for secure authentication.
