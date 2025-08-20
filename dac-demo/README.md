# DAC Demo - Custom Detection Rules

This directory contains custom detection rules for the Detection as Code demo.

## Directory Structure

```
dac-demo/
├── rules/          # Your custom detection rules (TOML format)
├── docs/           # Documentation for custom rules
└── README.md       # This file
```

## Adding Custom Rules

1. Create your detection rule in TOML format in the `rules/` directory
2. Follow the standard detection-rules schema
3. Test your rules locally before committing

## Testing Custom Rules Locally

```bash
# Set up environment
cd dac-demo-detection-rules
source env/bin/activate

# Export rules from Kibana
python -m detection_rules kibana --space default export-rules \
  --directory dac-demo/rules/ --custom-rules-only --strip-version

# Validate custom rules (if needed)
python -m detection_rules validate-rule dac-demo/rules/*.toml
```

## Deployment Workflow

### Feature Branch → Development
1. Create a feature branch: `git checkout -b feature/your-rule-name`
2. Add your rule to `dac-demo/rules/`
3. Push to GitHub: `git push origin feature/your-rule-name`
4. GitHub Actions automatically creates PR and deploys to Development

### Main Branch → Production
1. Create a Pull Request from dev to main
2. After PR approval and merge, GitHub Actions deploys to Production

## Rule Template

```toml
[metadata]
creation_date = "$(date -u +%Y/%m/%d)"
maturity = "development"
updated_date = "$(date -u +%Y/%m/%d)"

[rule]
author = ["Your Organization"]
description = """
Description of what this rule detects
"""
from = "now-6m"
index = ["logs-*", "filebeat-*"]
language = "kuery"
license = "Elastic License v2"
name = "Your Rule Name"
risk_score = 47
rule_id = "unique-uuid-here"
severity = "medium"
tags = ["Custom", "Your-Tags"]
timestamp_override = "event.ingested"
type = "query"

query = '''
your.query: here
'''

[[rule.threat]]
framework = "MITRE ATT&CK"
[[rule.threat.technique]]
id = "T1059"
name = "Command and Scripting Interpreter"
reference = "https://attack.mitre.org/techniques/T1059/"
```
