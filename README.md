# rk3588-bookworm-test

[![Update packages](https://github.com/radxa-repo/rk3588-bookworm-test/actions/workflows/update.yaml/badge.svg)](https://github.com/radxa-repo/rk3588-bookworm-test/actions/workflows/update.yaml)

## Content

* [Published GitHub Releases](pkgs.json)
* [File index](files.list)

## Usage

```bash
# Install signing keyring
keyring="$(mktemp)"
version="$(curl -L https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/VERSION)"
curl -L --output "$keyring" "https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/radxa-archive-keyring_${version}_all.deb"
sudo dpkg -i "$keyring"
rm -f "$keyring"
# Add apt package repo
sudo tee /etc/apt/sources.list.d/20-radxa.list <<< "deb [signed-by=/usr/share/keyrings/radxa-archive-keyring.gpg] https://radxa-repo.github.io/rk3588-bookworm-test/ rk3588-bookworm-test main"
sudo apt-get update
```
