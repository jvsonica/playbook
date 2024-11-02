# playbook

Ansible playbook to set up my workstation on Debian-based OS.

Execute with `ansible-playbook workstation.yml --ask-become-pass`.


## Structure
The playblook tasks are organized as follows:

`tasks/essentials.yml`: Installs essential packages using the package manager. Examples include curl, unzip, and fzf.

`tasks/update.yml`: Updates the package list and upgrades all installed packages. This includes running apt update && apt upgrade -y.

`tasks/applications/<app>.yml`: Installs specific applications, each with its own instructions. Examples include tasks/applications/chrome.yml and tasks/applications/vscode.yml.

`tasks/tools/<tool>.yml`: Installs specific tools, each with its own instructions. Examples include tasks/tools/zsh.yml, tasks/tools/nvim.yml, and tasks/tools/zoxide.yml.


## Testing

To test the playbook in a Docker container based on an Ubuntu image, follow these steps:

1. Build the Docker image using the provided Dockerfile in the repository:
```
docker build -t ansible-test .
```

2. Run the Docker container interactively, mounting the current directory to `/home/ansible_user/playbook` in the container:
```
docker run -it --rm -v "$(pwd)":/home/ansible_user/playbook ansible-test /bin/bash
```

Once inside the container, you can execute your Ansible playbook as needed:
```
ansible-playbook playbook/workstation.yml --ask-become-pass
```

## Future Work

- Also include:
  - zoxide
  - aws cli
  - rofi
  - clipboard manager (greenclip?)
  - obsidian

- Clone my dotfiles
- Ensure chrome task works properly, couldn't test it inside a container;
- Support for Arch-based system;

