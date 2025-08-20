# Custom Content Guide

This fork includes custom content not present in the original elastic/detection-rules repository.

## Quick Reference - What's Custom?

### Custom Additions:
\`\`\`
├── dac-demo/         ← CUSTOM: All custom content
│   ├── rules/                   ← CUSTOM: Your detection rules
│   ├── workflows/               ← CUSTOM: Workflow documentation  
│   └── docs/                    ← CUSTOM: Custom documentation
│
└── CUSTOM-CONTENT.md            ← CUSTOM: This file
\`\`\`

### Everything Else:
All other files and directories are from the original Elastic detection-rules repository.

## How to Add Custom Detection Rules

1. Create your rule in: \`dac-demo/rules/your-rule.toml\`
2. Test with: \`python -m detection_rules test dac-demo/rules/\`
3. Push to dev branch or create PR to main
