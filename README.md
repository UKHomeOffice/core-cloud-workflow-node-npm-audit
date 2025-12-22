# Core Cloud Workflow Node NPM Audit

A GitHub Actions workflow for running npm audit on Node.js projects to identify and report security vulnerabilities in dependencies.

## Overview

This workflow automates security scanning of npm packages within the core-cloud ecosystem, ensuring dependencies remain secure and up-to-date.

## Features

- Automated npm audit scanning
- Vulnerability reporting

## Requirements

- Valid `package.json` and `package-lock.json`

## Usage

Reference this workflow in your GitHub Actions pipeline:

```yaml
jobs:
    audit:
        uses: UKHomeOffice/core-cloud-workflow-node-npm-audit
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `working_directory` | Directory to run npm audit in | No | `.` |
| `node_version` | Node version | No | `24` |
| `audit_level` | Node The minimum level of vulnerability for npm audit to exit with a non-zero exit code | No | `low` |

## Outputs

| Output | Description |
|--------|-------------|
| `npm_audit_exit_code` | Exit code from npm audit (0 = success) |

## Updated Repository Structure
```
core-cloud-workflow-node-npm-audit/
.github
├── workflows
|    └── self-test.yaml
|
├── action.yaml
├── CODEOWNERS
├── README.md
└── tests
    ├── test-audit-invalid/
    └── test-audit-valid/
```

### 📘 SonarQube Configuration 
– `sonar-project.properties`

```
sonar.exclusions=tests/**

```

This removes all test fixtures and example IaC from SonarQube analysis, ensuring the Quality Gate only evaluates the actual workflow, action code, and scripts.

| Directory           | Purpose                                               | Excluded From SAST? |
| ------------------- | ----------------------------------------------------- | ------------------- |
| `tests/**`          | Local npm lint test harness (intentionally invalid code) | ✅ Yes               |
| `action.yaml`       | Composite action logic                                | ❌ No                |

This setup ensures clean SAST results without blocking PRs due to intentionally invalid IaC.

## Contributing

Please read [CONTRIBUTING.md](./CONTRIBUTING.md)

## Security

Please read [SECURITY.md](./SECURITY.md)