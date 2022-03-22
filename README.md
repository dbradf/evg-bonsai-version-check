# Evg Bonsai pot for checking version number has been updated

This [evg-bonsai](https://github.com/dbradf/evg-bonsai) pot supports checking that changes do
not conflict against published version. It uses the
[pypi-version-check](https://github.com/dbradf/pypi-version-check) tool to check that the
version number and changelog have been updated.

## Usage

Example landscape file:

```yaml
bonsai:
  - source: github
    owner: dbradf
    repo: evg-bonsai-version-check

tasks:
  - name: check_version
    commands:
    - bonsai: version-check:run
      params:
        target_dir: src
        package_type: python-poetry
        publish_type: pypi
```

## Parameters

The following parameters should be provided:

* **target_dir**: Directory containing the project configuration (e.g. pyproject.toml or Cargo.toml).
* **package_type**: Type of package being published. Options: `python-poetry`, `rust`.
* **publish_type**: Where packages are being published to. Options: `pypi`, `github-release`.
