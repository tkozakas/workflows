# workflows

Reusable GitHub Actions workflow for building multi-arch Docker images, pushing them to GHCR, and triggering a deploy webhook.

## Usage

```yaml
jobs:
  pipeline:
    uses: tkozakas/workflows/.github/workflows/stack-pipeline.yml@main
    secrets:
      deploy-token: ${{ secrets.DEPLOY_TOKEN }}
      deploy-url: ${{ secrets.DEPLOY_URL }}
```

Inputs: `image-suffix` (default `""`), `context` (default `.`), `dockerfile` (default `deploy/Dockerfile`). Both secrets are optional; the deploy job is skipped when either is empty.
