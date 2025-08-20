# dac-demo - Custom Detection Rules and Workflows

This directory contains all customizations specific to this fork of elastic/detection-rules.

## Directory Structure

\`\`\`
dac-demo/
├── rules/          # Your custom detection rules go here
├── workflows/      # Custom CI/CD workflows documentation
├── docs/          # Documentation for custom rules and processes
└── README.md      # This file
\`\`\`

## Testing Custom Rules

\`\`\`bash
# Validate custom rules
python -m detection_rules validate --rules-dir dac-demo/rules/

# Test custom rules
python -m detection_rules test dac-demo/rules/
\`\`\`
