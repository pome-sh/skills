# Security

## Reporting a vulnerability

Please do not open a public issue for a security problem.

- Preferred: [open a private vulnerability report](https://github.com/pome-sh/skills/security/advisories/new) on pome-sh/skills. Only the maintainers can see it.
- Email: founders@pome.sh.

Tell us what you found, how to reproduce it, and which version (`pome --version`) or skill. We acknowledge every report, work on a fix in private, and credit you in the release note if you want to be named. There is no bounty programme.

## What is in scope

- The `@pome-sh/cli` package: the `pome` command and the twin runtimes it bundles. That includes code execution through untrusted task, agent or config input, a path that leaks an API key (the credentials file, the Keychain, a log line), and a way around `pome login` or the hosted client's authentication.
- The published npm artifact and the dependencies it ships.

The coach skills in pome-sh/skills are samples. A problem in one of them is still worth a report, but it is not a vulnerability in the product.

Out of scope: a problem that needs local shell access to the user's machine already, and a theoretical issue without a working proof of concept on a supported platform. A problem in a hosted service (`api.pome.sh`, `app.pome.sh`, `docs.pome.sh`) goes to founders@pome.sh.

## What the twins are, and are not

A twin is a local, stateful stand-in for a vendor API, bound to loopback by default. It is a test fixture, not a service to expose on a network. The security model that matters: every session route requires a bearer minted from `TWIN_AUTH_SECRET`, the admin routes refuse callers they cannot identify, and a twin never serves the public dev secret unless you opt in with `POME_ALLOW_DEV_SECRETS=1`. If you find a way around any of that, report it.

Seeds and tapes can contain data you put there. Treat `.pome/`, `.pome-data/` and any tape you export the way you treat credentials.

## Credential handling

The CLI stores team API keys in the macOS Keychain when it is available, and otherwise in `~/.pome/credentials.json` with mode `0600`. It never reads, sends or logs `ANTHROPIC_API_KEY` or another provider's key: your agent's own process reads those from its environment.

## Supported versions

The latest version published to npm. Fixes ship as a new release rather than as patches to older versions.

The `pome-sh` package on npm is not this package and is not maintained. Install `@pome-sh/cli`.
