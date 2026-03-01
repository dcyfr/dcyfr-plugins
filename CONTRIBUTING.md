<!-- TLP:CLEAR -->
# Contributing to dcyfr-plugins

Thank you for contributing to the DCYFR Plugin Marketplace!

## Prerequisites

- Node.js ≥ 20
- `@dcyfr/ai` ≥ 2.0.0
- A GitHub account

## Plugin Structure

```
your-plugin/
├── .claude-plugin/
│   └── manifest.json        # Required: plugin manifest
├── src/
│   └── index.ts             # Plugin entry point
├── tests/
│   └── index.test.ts        # Unit tests (≥80% coverage)
├── sbom.json                # CycloneDX Software Bill of Materials
├── trust-score.json         # Trust score metadata
├── README.md
├── package.json
├── tsconfig.json
└── LICENSE
```

## manifest.json Schema

```json
{
  "plugin_id": "your-org/your-plugin",
  "name": "your-plugin",
  "version": "1.0.0",
  "description": "What your plugin does",
  "author": "your-org",
  "license": "MIT",
  "capabilities": ["capability_1", "capability_2"],
  "permissions": {
    "read": ["project_files"],
    "write": [],
    "network": false,
    "filesystem": "read-only"
  },
  "entrypoint": "src/index.ts",
  "minFrameworkVersion": "2.0.0",
  "keywords": ["quality"]
}
```

## Security Requirements

- No hardcoded secrets, API keys, or credentials
- No network access unless declared in `permissions.network: true`
- All dependencies must have SPDX-compatible licenses
- No critical or high CVEs in dependencies

## Submission Process

1. Fork this repository
2. Create a new directory at `plugins/<your-plugin-name>/`
3. Add all required files
4. Open a PR — automated security scan runs automatically
5. Address any findings from the security scan
6. A DCYFR team member will review and merge

## Automated Checks

All PRs automatically run:
- Secret detection (regex + entropy analysis)
- Vulnerability scan (npm audit + Grype)
- License validation (SPDX compatibility)
- SBOM presence check
- Trust score validation (minimum 70)
- Permission validation

## Questions?

Open an issue or email hello@dcyfr.ai
