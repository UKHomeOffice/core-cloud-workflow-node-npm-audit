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


## Contributing

Follow core-cloud contribution guidelines when updating this workflow.
