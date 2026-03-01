<!-- TLP:CLEAR -->
# dcyfr-plugins

**Official DCYFR Plugin Marketplace** — curated, security-scanned plugins for the [`@dcyfr/ai`](https://www.npmjs.com/package/@dcyfr/ai) framework.

[![Security Scan](https://github.com/dcyfr/dcyfr-plugins/actions/workflows/plugin-security-scan.yml/badge.svg)](https://github.com/dcyfr/dcyfr-plugins/actions/workflows/plugin-security-scan.yml)

---

## 🔌 What is this?

This repository is the official registry for DCYFR plugins — extensions that add capabilities (linting, security scanning, API validation, etc.) to AI agents built with `@dcyfr/ai`.

Every plugin in this registry has been:
- ✅ Automatically security-scanned (secrets, vulnerabilities, malware)
- ✅ Assigned a trust score (0–100)
- ✅ Verified for SPDX license compliance
- ✅ Provided with a Software Bill of Materials (SBOM)

---

## 📦 Available Plugins

| Plugin | Version | Trust Score | Capabilities |
|--------|---------|-------------|--------------|
| [code-quality-checker](plugins/code-quality-checker/) | 1.0.0 | 95 | `code_quality`, `linting` |
| [secret-detector](plugins/secret-detector/) | 1.2.0 | 98 | `security`, `secret_scanning` |
| [license-compliance](plugins/license-compliance/) | 1.1.0 | 92 | `compliance`, `license_validation` |
| [sbom-generator](plugins/sbom-generator/) | 1.0.0 | 90 | `sbom`, `dependency_analysis` |
| [vulnerability-scanner](plugins/vulnerability-scanner/) | 2.0.0 | 96 | `security`, `vulnerability_scanning` |
| [design-token-validator](plugins/design-token-validator/) | 1.0.0 | 88 | `ui_quality`, `design_tokens` |
| [test-coverage-gate](plugins/test-coverage-gate/) | 1.1.0 | 91 | `testing`, `coverage_enforcement` |
| [dependency-auditor](plugins/dependency-auditor/) | 1.3.0 | 94 | `security`, `dependency_audit` |
| [performance-budget](plugins/performance-budget/) | 1.0.0 | 85 | `performance`, `web_vitals` |
| [tlp-classifier](plugins/tlp-classifier/) | 1.0.0 | 93 | `compliance`, `tlp_classification` |
| [accessibility-checker](plugins/accessibility-checker/) | 1.0.0 | 87 | `accessibility`, `wcag_validation` |
| [api-schema-validator](plugins/api-schema-validator/) | 1.2.0 | 89 | `api_quality`, `schema_validation` |

---

## 🚀 Usage

```typescript
import { PluginLoader } from '@dcyfr/ai';

const loader = new PluginLoader();
await loader.loadFromMarketplace('dcyfr/dcyfr-plugins', 'secret-detector');
```

---

## 📋 Submission Guidelines

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to submit your plugin. All submissions require a valid `manifest.json`, passing security scan, and SPDX-compatible license.

---

**Maintained by [DCYFR Labs](https://www.dcyfr.ai)** | Contact: hello@dcyfr.ai
