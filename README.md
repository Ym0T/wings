[![Logo Image](https://cdn.pterodactyl.io/logos/new/pterodactyl_logo.png)](https://pterodactyl.io)

[![Push](https://github.com/Ym0T/wings/actions/workflows/push.yaml/badge.svg?branch=develop)](https://github.com/Ym0T/wings/actions/workflows/push.yaml)
[![Docker](https://github.com/Ym0T/wings/actions/workflows/docker.yaml/badge.svg?branch=develop)](https://github.com/Ym0T/wings/actions/workflows/docker.yaml)
[![CodeQL](https://github.com/Ym0T/wings/actions/workflows/codeql.yaml/badge.svg?branch=develop)](https://github.com/Ym0T/wings/actions/workflows/codeql.yaml)
[![Go Report Card](https://goreportcard.com/badge/github.com/ym0t/wings)](https://goreportcard.com/report/github.com/ym0t/wings)

# Wings (ym0t fork)

This is an independently maintained fork of [pterodactyl/wings](https://github.com/pterodactyl/wings), carrying the
same Minecraft server version detection feature as [0x7d8/wings](https://github.com/0x7d8/wings).

Wings is Pterodactyl's server control plane, built for the rapidly changing gaming industry and designed to be
highly performant and secure. Wings provides an HTTP API allowing you to interface directly with running server
instances, fetch server logs, generate backups, and control all aspects of the server lifecycle.

In addition, Wings ships with a built-in SFTP server allowing your system to remain free of Pterodactyl specific
dependencies, and allowing users to authenticate with the same credentials they would normally use to access the Panel.

## Why this fork?

[0x7d8/wings](https://github.com/0x7d8/wings) is a fork of [pterodactyl/wings](https://github.com/pterodactyl/wings)
that adds Minecraft server version detection. This repository carries the same feature, independently maintained —
meaning changes from pterodactyl/wings have to be manually merged into both forks over time.

Since neither fork is guaranteed to always be fully up to date, this repo exists as a redundant alternative:
if [0x7d8/wings](https://github.com/0x7d8/wings) is ahead, use that — if this one is, use this. By not being a
GitHub fork of 0x7d8/wings, there are no upstream constraints on when and what gets merged.

## ⬇️ Download

Binaries are automatically built from the `develop` branch on every push.  
The `_debug` variants include debug symbols — only needed for troubleshooting.

| Platform | Normal | Debug |
|----------|--------|-------|
| Linux x86_64 (amd64) | [wings_linux_amd64](https://nightly.link/Ym0T/wings/workflows/push.yaml/develop/wings_linux_amd64.zip) | [wings_linux_amd64_debug](https://nightly.link/Ym0T/wings/workflows/push.yaml/develop/wings_linux_amd64_debug.zip) |
| Linux ARM64 | [wings_linux_arm64](https://nightly.link/Ym0T/wings/workflows/push.yaml/develop/wings_linux_arm64.zip) | [wings_linux_arm64_debug](https://nightly.link/Ym0T/wings/workflows/push.yaml/develop/wings_linux_arm64_debug.zip) |

### Quick Install

```bash
curl -L -o /tmp/wings.zip \
  "https://nightly.link/Ym0T/wings/workflows/push.yaml/develop/wings_linux_$([ "$(uname -m)" = "x86_64" ] && echo amd64 || echo arm64).zip" \
  && unzip -o /tmp/wings.zip -d /usr/local/bin \
  && chmod +x /usr/local/bin/wings \
  && rm /tmp/wings.zip \
  && systemctl restart wings \
  && wings version
```

> ⚠️ These are development builds from the `develop` branch. Use at your own risk.

## Documentation

* [Panel Documentation](https://pterodactyl.io/panel/1.0/getting_started.html)
* [Wings Documentation](https://pterodactyl.io/wings/1.0/installing.html)
* [Community Guides](https://pterodactyl.io/community/about.html)
* [Discord](https://discord.gg/pterodactyl)

## Reporting Issues

For issues specific to this fork, open an issue in this repository. For upstream bugs that affect the original
pterodactyl/wings, please also report them at [pterodactyl/panel](https://github.com/pterodactyl/panel).
