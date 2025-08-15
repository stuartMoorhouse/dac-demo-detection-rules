# Custom Content Guide - DAC Demo

This fork includes custom content for the Detection as Code (DAC) demo that is not present in the original elastic/detection-rules repository.

## What is DAC (Detection as Code)?

Detection as Code is a methodology where security detection rules are:
- Written and stored as code (TOML files)
- Version controlled in Git
- Tested automatically via CI/CD
- Deployed programmatically to security tools

## Quick Reference - What's Custom?

### Custom Additions:
```
├── .github/workflows/
│   └── ci.yml                    ← CUSTOM: Simplified CI/CD pipeline
│
├── dac-demo/                     ← CUSTOM: All DAC demo content
│   ├── rules/                   ← CUSTOM: Your detection rules
│   ├── workflows/               ← CUSTOM: Workflow documentation  
│   └── docs/                    ← CUSTOM: Custom documentation
│
└── CUSTOM-CONTENT.md            ← CUSTOM: This file
```

### Everything Else:
All other files and directories are from the original Elastic detection-rules repository and should not be modified directly.

## How to Add Custom Detection Rules

### 1. Create your rule in the dac-demo/rules folder:
```bash
# Create a new custom rule
dac-demo/rules/suspicious-login-attempt.toml
```

### 2. Test your custom rules:
```bash
# Validate custom rules
python -m detection_rules validate --rules-dir dac-demo/rules/

# Test custom rules
python -m detection_rules test dac-demo/rules/
```

### 3. Push and let CI/CD validate:
```bash
git add dac-demo/rules/
git commit -m "Add custom rule: suspicious login attempt"
git push origin dev  # or create a PR to main
```

## Syncing with Upstream Elastic

```bash
# Get latest Elastic rules without losing your custom content
git fetch upstream
git checkout main  
git merge upstream/main

# Your dac-demo/ directory won't conflict
```

## Branch Strategy

- **main**: Production rules (protected, requires PR)
- **dev**: Development (direct push allowed)

## Questions?

See `dac-demo/README.md` for detailed information about the custom content structure.