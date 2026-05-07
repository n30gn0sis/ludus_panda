# ludus_panda Ansible Role

Installs [PANDA](https://panda.re/) onto Debian/Ubuntu systems for Ludus environments.

## Role Variables

See `defaults/main.yml` for all variables.

### Deployment and build method

- `ludus_panda_install_method`: choose `binary`, `source`, or `container`.
- `ludus_panda_version`: PANDA release version (without leading `v`) or `latest`.
- `ludus_panda_arch`: release architecture suffix (`amd64`, `arm64`, etc.).

### Binary deployment options

- `ludus_panda_release_url`: source archive URL template.
- `ludus_panda_checksum`: optional archive checksum (`sha256:...`).
- `ludus_panda_force_reinstall`: force refresh of downloaded artifact.
- `ludus_panda_install_dir`: installation directory (default `/opt/panda`).
- `ludus_panda_manage_profile_path`: manage `/etc/profile.d/panda.sh`.

### Source-build options

- `ludus_panda_source_repo`: PANDA git repository URL.
- `ludus_panda_source_ref`: branch, tag, or commit ref.
- `ludus_panda_build_dir`: checkout/build directory.
- `ludus_panda_build_type`: e.g. `Release` or `Debug`.
- `ludus_panda_build_jobs`: build parallelism.
- `ludus_panda_build_targets`: optional build target list.
- `ludus_panda_enable_plugins` / `ludus_panda_disable_plugins`: plugin toggles.
- `ludus_panda_source_apt_packages`: dependencies for compiling from source.

> Note: `source` and `container` install methods are currently placeholders and intentionally fail until implementation tasks are added.

### Python / pandare options

- `ludus_panda_install_pandare`: install Python `pandare` package.
- `ludus_panda_pandare_package`: pip package name.
- `ludus_panda_pandare_version`: optional version pin.
- `ludus_panda_virtualenv_path`: optional virtualenv path.
- `ludus_panda_pip_index_url`: optional custom pip index.

## Example Playbook

```yaml
- hosts: all
  become: true
  roles:
    - role: ludus_panda
      vars:
        ludus_panda_install_method: "binary"
        ludus_panda_version: "latest"
        ludus_panda_arch: "amd64"
        ludus_panda_install_pandare: true
```

## Ludus Usage

Reference this role in your Ludus range config as you would any custom Ansible role.
