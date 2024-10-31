# playbook

Ansible playbook to set up my workstation on Debian-based OS.

Execute with `ansible-playbook workstation.yml --ask-become-pass`.

## Future Work

- Also include:
  - ohmyzsh
  - zsh plugins like autosuggestions and syntax highlight
  - zsh plugin for ctrl r with fzf
  - nvim
  - nerdfont
  - golang
  - spotify
  - zoxide
  - starship
  - aws cli

- Support for Arch-based system;
- Clone my dotfiles
- Organization should be:
  - `tasks/essentials.yml` : installs packages through package manager only;
  - `tasks/applications/<app>.yml`: installs <app> with its own instructions;
  - `tasks/applications.yml`: imports tasks defined in `applications` dir;
