# Custom Workflows

This directory documents our custom GitHub Actions workflows.

## Active Custom Workflows

### ci.yml
- **Location**: `.github/workflows/ci.yml`
- **Purpose**: Simplified CI/CD pipeline for detection rules validation
- **Created**: For DAC demo purposes
- **Triggers**: Push to main/dev, Pull requests

This workflow is our custom addition and not part of the original Elastic detection-rules repository.

## Why Workflows Stay in .github/workflows/

GitHub Actions only recognizes workflows in `.github/workflows/`, so our custom workflows must remain there to function. This directory serves as documentation and reference for what we've added.

## Identifying Custom Workflows

Our custom workflows in `.github/workflows/` are:
- `ci.yml` - Our simplified CI/CD pipeline

All other workflows in that directory are from the original Elastic repository.