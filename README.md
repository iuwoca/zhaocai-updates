# Zhaocai Updates

This public repository hosts update manifests and release assets for Zhaocai.

## Download Proxies

Clients read `download-proxies.json` before downloading an update. Change the
ordered `download_proxy_prefixes` list to switch providers without rebuilding
the Windows or macOS application. Each prefix must use HTTPS and is prepended
to the original GitHub Release asset URL.

Use an empty list to disable download proxies and use GitHub directly:

```json
{
  "download_proxy_prefixes": []
}
```

The client always keeps the original GitHub URL as the final fallback.

## macOS Build Action

The `Build macOS Release` workflow builds the macOS shell and publishes it to this repository's Release assets as:

```text
zhaocai_shell_macos.app.zip
```

It also updates:

```text
latest-macos.json
```

Required repository secrets:

- `SOURCE_REPO_TOKEN`: a GitHub token with `repo` read access to `iuwoca/zhaocai`, `iuwoca/pgy`, and `iuwoca/python_qt_jixing`
- `ZHAOCAI_AES_KEY_HEX`: the 64-character AES key used by the zhaocai shell

Run it from GitHub Actions with:

```text
Actions -> Build macOS Release -> Run workflow
```

Use the same version as `zhaocai/version.py`, for example `1.0.10`. Users download `招财系统.app.zip`, unzip it, and open `招财系统.app`.
