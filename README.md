# GLP Server Panel — Releases

This repository publishes **Windows installer releases of GLP Server Panel**.
It holds releases only: no source code, no keys, no secrets.

The panel's built-in updater reads this repository's GitHub Releases:

- A release counts when its tag is a version (`v1.0.0`, `v1.0.0-rc10`) and it
  carries both assets:
  - `GLP-Server-Panel-Setup.exe`, the installer
  - `SHA256SUMS.txt`, the SHA-256 of the installer (`<sha256>  GLP-Server-Panel-Setup.exe`)
- The panel shows an update pop-up with **Update now**, **Skip this version** and
  **Schedule for later**. Update now downloads from GitHub only, refuses an
  installer whose SHA-256 doesn't match `SHA256SUMS.txt`, stops running servers
  gracefully, runs the installer silently after one Windows permission prompt,
  reopens the panel and starts those servers again. Settings, servers and worlds
  are kept.
- Pre-releases (`-rcN`) are offered only to panels already running a pre-release.

The installers are not code-signed yet, so Windows SmartScreen may warn the
first time an installer is run by hand.
