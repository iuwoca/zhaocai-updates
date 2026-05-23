# Zhaocai Updates

This public repository hosts update manifests and release assets for Zhaocai.

## macOS Build Action

The `Build macOS Release` workflow builds the macOS shell and publishes it to this repository's Release assets as:

```text
zhaocai_shell_macos
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

Use the same version as `zhaocai/version.py`, for example `1.0.10`.
