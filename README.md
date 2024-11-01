# playbook

Ansible playbook to set up my workstation on Debian-based OS.

Execute with `ansible-playbook workstation.yml --ask-become-pass`.

## Future Work

- Also include:
  - nerdfont
  - golang
  - spotify
  - zoxide
  - starship
  - aws cli
  - rofi
  - clipboard manager (greenclip?)
  - delta (git diff)

- Clone my dotfiles
- Organization should be:
  - `tasks/essentials.yml` : installs packages through package manager only;
  - `tasks/applications/<app>.yml`: installs <app> with its own instructions;
  - `tasks/tools/<tool>.yml`: installs <tool> with its own instructions;
- Support for Arch-based system;

