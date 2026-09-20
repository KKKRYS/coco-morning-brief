# Coco Morning Brief

Production site: https://coco-morning-brief.surge.sh

## Deployment

This repository is configured so changes under `public/` deploy automatically to Surge through GitHub Actions.

### One-time Surge token setup

On your Mac terminal:

```bash
surge tokens add --domain coco-morning-brief.surge.sh -m "github actions"
```

Copy the token shown once, then in GitHub open:

`Settings → Secrets and variables → Actions → New repository secret`

Create:

- Name: `SURGE_TOKEN`
- Value: the scoped Surge token

Do not commit the token into the repository.

## Daily update architecture

Target flow:

`07:30 Asia/Shanghai → research latest verified data/news → update public/index.html → save public/archive/YYYY-MM-DD.html → push to main → GitHub Actions deploys to Surge`

The deployment workflow is already installed. The daily content update can be driven by ChatGPT Work / scheduled automation once the repository is available to the task.
