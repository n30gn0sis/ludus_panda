# ludus_panda Ansible Role

Installs [PANDA](https://panda.re/) onto Debian/Ubuntu systems for Ludus environments.

## Role Variables

See `defaults/main.yml` for all variables. Common options:

- `ludus_panda_version`: PANDA release tag (for example `v0.0.0`) or `latest`
- `ludus_panda_arch`: release architecture suffix (`amd64`, `arm64`, etc.)
- `ludus_panda_install_dir`: installation directory (default `/opt/panda`)
- `ludus_panda_archive_checksum`: optional checksum (`sha256:<hex>`) for deterministic verification
- `ludus_panda_install_pandare`: install Python `pandare` package

## Example Playbook

```yaml
- hosts: all
  become: true
  roles:
    - role: ludus_panda
      vars:
        ludus_panda_version: "latest"
        ludus_panda_arch: "amd64"
```

## Ludus Usage

Reference this role in your Ludus range config as you would any custom Ansible role.
