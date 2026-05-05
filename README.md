# Ludus PANDA Role

This repository provides a Ludus-focused Ansible role for installing
[PANDA](https://panda.re/) on Debian/Ubuntu targets.

## Layout

- `roles/ludus_panda/` – role implementation

## Next Steps

1. Adjust default version/architecture values in `defaults/main.yml` for your targets.
2. Add any Ludus-specific inventory/group vars used in your environment.
3. Validate in your Ludus lab with an apply run.
