# Security Policy

This repository is public. Treat every commit, file name, comment, diagram, and historical revision as publicly accessible.

## Never publish

- Passwords, password hashes, usernames paired with secrets, API tokens, certificates, private keys, or authentication material
- MikroTik binary backups or unreviewed full configuration exports
- Real public/private IP allocations, customer details, contact information, hostnames, or identifiable topology data
- Employer, customer, provider, or third-party documents without explicit authorization
- Logs, screenshots, monitoring exports, or diagrams that reveal internal infrastructure
- Confidential service inventories, bandwidth allocations, or operational procedures

## Safe publication practices

- Use documentation prefixes, private lab ranges, fictional ASNs, and neutral labels.
- Publish only reviewed, purpose-built examples or sanitized excerpts.
- Check configuration dependencies and remove operational identifiers before committing.
- Review the complete diff, not only the files changed in the editor.
- Scan files and Git history for secrets before publishing.
- Do not assume that changing an IP address or hostname alone makes a configuration safe to disclose.

## Automated scanning and commit identity

The repository runs a GitHub Actions secret scan on pushes and pull requests. A successful scan is useful evidence, but it does not replace manual review of configuration semantics, repository history, screenshots, or third-party material.

Use the GitHub-provided noreply address for Git commits. Enable GitHub's email privacy and push-protection options, then verify new commit metadata before publishing. Rewriting old commits is a separate, disruptive operation and must be followed by a force-push of all affected refs.

## Validation

Configuration examples are educational references. Review syntax and feature support for the target software release, and test in an isolated lab before operational use.

## Reporting a concern

If you identify a credential, sensitive identifier, or other security concern, please report it privately to the repository owner rather than opening a public issue containing the sensitive material.
