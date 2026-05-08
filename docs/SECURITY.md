# DiamOps Showcase Security Policy

This repository is public-safe by design.

Do not commit:

- `.env` files
- credentials
- API keys
- databases
- generated reports
- storage or export folders
- admin templates
- deployment configs
- internal validation logs
- private roadmap files

Before publishing, run:

```powershell
rg -n --hidden -S "SECRET_KEY|PASSWORD|TOKEN|API_KEY|DATABASE_URL|PRIVATE_KEY|sk-|ghp_|github_pat_" .
rg -n --hidden -S "\.env|sqlite|storage|exports|render.yaml|Procfile|admin" .
```

