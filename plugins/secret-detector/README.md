<!-- TLP:CLEAR -->
# secret-detector

**Trust Score: 98/100** | v1.2.0 | MIT

Detects hardcoded secrets and API keys using regex and Shannon entropy analysis.

## Detection Patterns
- AWS access keys, GitHub PATs, Stripe API keys
- Generic high-entropy strings (≥3.5 entropy)
- Private keys (RSA, EC, PEM), DB connection strings

## Configuration
```json
{ "secretDetector": { "entropyThreshold": 3.5, "allowlist": ["test-*"] } }
```
