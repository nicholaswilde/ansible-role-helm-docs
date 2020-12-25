# Ansible Role: helm-docs

[![CI](https://github.com/nicholaswilde/ansible-role-helm-docs/workflows/CI/badge.svg?event=push)](https://github.com/nicholaswilde/ansible-role-helm-docs/actions?query=workflow%3ACI)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![GitHub](https://img.shields.io/github/license/nicholaswilde/ansible-role-helm-docs)](https://github.com/nicholaswilde/ansible-role-helm-docs/blob/main/LICENSE)

This role installs the [helm-docs](https://github.com/norwoodj/helm-docs/) binary on any supported host.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see [defaults/main.yaml](./defaults/main.yaml)):

    app_ver: '1.4.0'
    app_platform: linux
    app_arch: x86_64

Controls for the version of Helm to be installed. See [available helm-docs releases](https://github.com/norwoodj/helm-docs/releases/). You can upgrade or downgrade versions by changing the `app_ver`.

    app_install_dir: /usr/local/bin

The location where the helm-docs binary will be installed.

## Dependencies

- [andrewrothstein.unarchive-deps](https://galaxy.ansible.com/andrewrothstein/unarchive-deps)

Install dependencies

    $ ansible-galaxy role install -r requirements.yaml

## Example Playbook

    - hosts: all
      roles:
        - role: nicholaswilde.helm-docs

## Testing

If you want to use [moleculte](https://molecule.readthedocs.io/en/latest/installation.html) to test, be sure to check out the repo in a folder titled `nicholaswilde.helm-docs`

```
# Checkout
$ git clone https://github.com/nicholaswilde/ansible-role-helm-docs.git nicholaswilde.helm-docs
$ cd nicholaswilde.helm-docs
# Test
$ molecule test
# Converge
$ molecule converge
```

## Pre-commit hook

If you want to automatically lint the files with a pre-commit hook, make sure you
[install the pre-commit binary](https://pre-commit.com/#install), and add a [.pre-commit-config.yaml file](./.pre-commit-config.yaml)
to your project. Then run:

```bash
$ pre-commit install
$ pre-commit install-hooks
```

## Inspiration

Inspiration for this repository has been taken from [Andrew Rothstein](https://github.com/andrewrothstein) and [Jeff Geerling](https://github.com/geerlingguy/).

## License

[Apache 2.0 License](./LICENSE)

## Author Information

This project was started in 2020 by [Nicholas Wilde](https://github.com/nicholaswilde/).
