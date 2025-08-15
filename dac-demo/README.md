# DAC Demo - Custom Detection Rules and Workflows

This directory contains all customizations specific to the DAC (Detection as Code) demo fork of elastic/detection-rules.

## Directory Structure

```
dac-demo/
├── rules/          # Your custom detection rules go here
├── workflows/      # Custom CI/CD workflows documentation
├── docs/          # Documentation for custom rules and processes
└── README.md      # This file
```

## What Goes Here

### ✅ PUT HERE:
- Your organization's custom detection rules
- Custom CI/CD workflows (like our demo CI)
- Documentation specific to your implementation
- Test files for your custom rules
- Configuration specific to your environment

### ❌ DON'T PUT HERE:
- Modifications to Elastic's original rules (use pull requests upstream instead)
- Elastic's official workflows
- Core detection-rules framework code

## Custom Rules Naming Convention

When creating custom rules, use this naming pattern:
- `custom-[category]-[description].toml`
- Example: `custom-network-suspicious-rdp.toml`

## Keeping in Sync with Upstream

```bash
# Fetch latest from Elastic
git fetch upstream
git checkout main
git merge upstream/main

# Your custom content in /dac-demo/ won't conflict
```

## Custom Workflows

- `ci.yml` - Simplified CI/CD for demo purposes

## Testing Custom Rules

```bash
# Test only custom rules
python -m detection_rules test dac-demo/rules/

# Validate custom rules
python -m detection_rules validate --rules-dir dac-demo/rules/
```