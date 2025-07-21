# safe-chain-test

**This project is intentionally crafted to test if [Aikido Safe Chain](https://github.com/aikidosec/safe-chain) is installed and working correctly.**

## ⚠️ WARNING
This repository contains code that *appears* suspicious or malicious, but is completely harmless. Its only purpose is to trigger Aikido Safe Chain's malware detection and verify your setup.

---

## What is Aikido Safe Chain?

The Aikido Safe Chain prevents developers from installing malware on their workstations through npm, npx, or yarn.

The Aikido Safe Chain wraps around the npm cli, npx, and yarn to provide extra checks before installing new packages. This tool will detect when a package contains malware and prompt you to exit, preventing npm, npx, or yarn from downloading or running the malware.

### Supported Package Managers
- ✅ npm
- ✅ npx
- ✅ yarn
- 🚧 pnpm Coming soon

### Installation
1. Install the Aikido Safe Chain package globally using npm:
   ```sh
   npm install -g @aikidosec/safe-chain
   ```
2. Setup the shell integration by running:
   ```sh
   safe-chain setup
   ```
   ❗Restart your terminal to start using the Aikido Safe Chain.
3. Verify the installation by running:
   ```sh
   npm install eslint-js
   ```
   The output should show that Aikido Safe Chain is blocking the installation of this package as it is flagged as malware.

When running npm, npx, or yarn commands, the Aikido Safe Chain will automatically check for malware in the packages you are trying to install. If any malware is detected, it will prompt you to exit the command.

### How it works
The Aikido Safe Chain works by intercepting the npm, npx, and yarn commands and verifying the packages against Aikido Intel - Open Sources Threat Intelligence.

The Aikido Safe Chain integrates with your shell to provide a seamless experience when using npm, npx, and yarn commands. It sets up aliases for these commands so that they are wrapped by the Aikido Safe Chain commands, which perform malware checks before executing the original commands. We currently support:

- ✅ Bash
- ✅ Zsh
- ✅ Fish
- ✅ PowerShell
- ✅ PowerShell Core

More information about the shell integration can be found in the shell integration documentation.

### Uninstallation
To uninstall the Aikido Safe Chain, you can run the following command:

1. Remove all aliases from your shell by running:
   ```sh
   safe-chain teardown
   ```
2. Uninstall the Aikido Safe Chain package using npm:
   ```sh
   npm uninstall -g @aikidosec/safe-chain
   ```
   ❗Restart your terminal to remove the aliases.

### Usage in CI/CD
🚧 Support for CI/CD environments is coming soon...

---

## Project Purpose
This project is **not** malicious. It is only for testing the Aikido Safe Chain installation. You can safely inspect the code in `index.js` to confirm that it does not perform any harmful actions. 