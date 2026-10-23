# Security Policy

## Scope
This repository contains mathematical research, experimental detector code, and reproducibility materials. Treat all empirical claims as unverified until independently reproducible. Do not put credentials, API tokens, private keys, personal data, or confidential research notes in tracked files or issues.

## Supported versions
Security fixes are considered for the default branch and the currently maintained research branch. This policy does not imply that every experiment is production-ready.

## Reporting a vulnerability
Please do not publish exploitable details in a public issue. Use GitHub's private vulnerability reporting feature if it is enabled for this repository, or contact the repository owner privately through a channel they have already published. Do not include secrets in the report.

## Secret exposure
If a credential is committed, revoke or rotate it immediately. Removing it from the latest commit is not sufficient: assume it may remain in Git history, forks, caches, and logs. Review GitHub Actions logs and any service using that credential.

## Research integrity
Security reports must distinguish a confirmed defect from a hypothesis. Do not run destructive experiments, access systems without authorization, or upload private datasets to issues or public artifacts.
