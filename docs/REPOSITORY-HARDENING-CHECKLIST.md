# Repository Hardening Checklist

This checklist is for the repository owner to apply and verify. Documentation in this repository does not itself change GitHub repository settings.

## Required protections
- [ ] Protect the default branch with a ruleset or branch protection rule.
- [ ] Require pull requests before merging; disallow direct pushes where practical.
- [ ] Require at least one approval if a trusted second reviewer is available. Do not use an unreviewed self-approval as a substitute.
- [ ] Require status checks after CI is configured and confirm the exact check names.
- [ ] Dismiss stale approvals after new commits; require conversation resolution.
- [ ] Block force pushes and branch deletion on the default branch.
- [ ] Restrict who can bypass the ruleset; keep bypass narrowly scoped.
- [ ] Keep the reconstruction branch and pull request unmerged until review and validation are complete.

## Account and repository security
- [ ] Enable two-factor authentication on the GitHub account.
- [ ] Review collaborators, outside collaborators, GitHub App installations, deploy keys, and personal access tokens; revoke anything unrecognized or unnecessary.
- [ ] Enable Dependabot alerts and security updates where available.
- [ ] Enable secret scanning and push protection where available on the plan/repository.
- [ ] Enable private vulnerability reporting if available.
- [ ] Review Actions permissions; use least privilege and pin third-party Actions to full commit SHAs before relying on them for security-sensitive workflows.
- [ ] Do not store secrets in repository files, commit messages, issues, pull-request text, or workflow logs. Use GitHub Actions secrets only when needed.

## Research-release controls
- [ ] Keep raw personal/private material out of public commits and artifacts.
- [ ] Require a reproducible command, expected output, and test record for every claimed computational result.
- [ ] Separate theorem statements from numerical observations and historical claims.
- [ ] Do not publish, merge, tag a release, or contact a journal on the owner's behalf without explicit approval.
- [ ] Before a release, inspect the full diff and Git history for secrets and private material.

## Verification record
Record the date, settings changed, and any settings unavailable on the account. Never mark a control enabled until it has been checked in GitHub settings.
