# Repository Guidelines

## Project Structure & Module Organization
This repository is a workspace that tracks multiple workshop projects as Git submodules. Each workshop lives in its own top-level folder and is versioned by a specific commit SHA.

- `20-min-lightning-workshop/`
- `bitcoin-nodejs-starter/`
- `developing-cln-plugins/`
- `lightning-address-workshop/`
- `lnd-interfacing-examples/`
- `lnurl-auth-example/`
- `lnurl-express-workshop/`
- `ndk-basics/`
- `nextjs_nostr_app_ndk_template/`
- `nwc-wallet-workshop/`
- `tips-for-scaling-express-api/`
- `voltage-mutinynet-workshop/`

Use submodules rather than copying code between workshops. Initialize them with:

```sh
git submodule update --init --recursive
```

## Build, Test, and Development Commands
There are no build or test commands at the workspace root. Run commands inside the relevant submodule instead, following that project’s README or `package.json`/`Makefile` (if present). Example:

```sh
cd ndk-basics
# then run that project’s local dev/test commands
```

## Coding Style & Naming Conventions
This repository does not enforce a single coding style at the root. Conventions live inside each submodule. Keep workshop directory names kebab-case and match the repository name. Avoid adding source files directly at the root; create or update content within the appropriate submodule.

## Testing Guidelines
No tests run at the root level. Execute tests within the target submodule using its documented tooling (e.g., `npm test`, `pytest`, `go test`, `cargo test`). If a workshop adds a new test suite, document the command in that submodule’s README.

## Commit & Pull Request Guidelines
Commit messages in this repo are short, imperative, and workshop-focused (e.g., “Add ndk-basics”, “update nextjs_nostr… to latest commit”). Follow that pattern when updating submodule references.

For PRs:
- Describe which submodules changed and why.
- Include the new submodule commit SHA(s).
- Note any access requirements (e.g., private submodules).

## Security & Configuration Tips
One submodule uses an SSH URL (`nwc-wallet-workshop`), which requires GitHub SSH access. Ensure your SSH keys are configured before initializing submodules.
