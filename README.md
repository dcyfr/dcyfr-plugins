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

## 🏗️ Plugin Structure

Every plugin in this registry follows a standard layout:

```
plugins/<name>/
  .claude-plugin/
    manifest.json       # name, version, capabilities, permissions, dcyfr compat range
  sbom.json             # CycloneDX SBOM — all runtime dependencies declared
  trust-score.json      # verified trust metrics (automated, do not edit manually)
  index.ts              # plugin entry point
  package.json
  README.md
  LICENSE
```

### Trust Score Breakdown

Scores are computed by the CI pipeline on every PR and re-verified on each release:

| Factor | Weight | Pass threshold |
|--------|--------|----------------|
| Security scan (secrets, vulns, malware) | 30% | 0 findings |
| Valid SPDX license | 20% | OSI-approved |
| SBOM completeness | 15% | 100% declared deps |
| Manifest validity | 15% | All required fields |
| Code quality (no `eval`/`exec`) | 10% | No violations |
| Author reputation | 10% | GitHub account ≥ 90 days |

**Minimum score for inclusion: 85.** Plugins scoring < 85 are rejected and the PR is closed automatically.

### Capabilities Reference

| Capability | What it signals |
|------------|----------------|
| `code_quality` | Analyses source code, suggests improvements |
| `security` | Detects vulnerabilities, secrets, or policy violations |
| `testing` | Enforces test coverage thresholds |
| `compliance` | License, TLP, or regulatory checks |
| `performance` | Web Vitals, bundle size, or runtime benchmarks |
| `accessibility` | WCAG 2.1 AA checks |
| `api_quality` | Schema validation, breaking-change detection |
| `ui_quality` | Design token compliance, visual regression |
| `sbom` | Generates or validates Software Bills of Materials |
| `dependency_analysis` | Audits transitive dependency trees |

---

## 📋 Submission Guidelines

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to submit your plugin. All submissions require a valid `manifest.json`, passing security scan, and SPDX-compatible license.

---

**Maintained by [DCYFR Labs](https://www.dcyfr.ai)** | Contact: hello@dcyfr.ai
