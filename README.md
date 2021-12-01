# reusable_workflows

## docker-buildimage.yml
### Build and push docker image to ECR
---
This requires a variable to be set in your caller workflow:

`ECR_REPOSITORY` needs to be assigned.

Example:
```
jobs:
  build-release:
    uses: chevrenoire/reusable_workflows/.github/workflows/docker-buildimage.yml@main
    with:
      ECR_REPOSITORY: YOUR_REPO_NAME
    secrets:
      AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
      AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      AWS_REGION: ${{ secrets.AWS_REGION }}
```
Hoping to find a way to better finesse this.