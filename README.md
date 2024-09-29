# storefront

The customer-facing web shop.

## Build and deployment

Every push to `main` builds the image `ghcr.io/process-agent-sandbox/storefront`, tagged
`sha-<first 7 characters of the commit>` (`.github/workflows/build.yml`).

Deployment is GitOps with Argo CD. The running version per environment is the image tag in
[storefront-deploy](https://github.com/process-agent-sandbox/storefront-deploy):
`envs/staging` and `envs/prod`. A pull request there that changes the tag is a deployment.
