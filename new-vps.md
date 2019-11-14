# New VPS Checklist (for Ubuntu)

- [ ] **(Restart required)** Change hostname (in `/etc/hostname`).
- [ ] Add user.
  - [ ] Add user (by `useradd`).
  - [ ] Set password (by `chpasswd`).
  - [ ] Enable sudo (by adding user to group `sudo`).
  - [ ] **Restart** and login as added user.
- [ ] Update and install softwares.
  - [ ] **(Optional)** Update source.list.
  - [ ] Update softwares (by `apt update` and `apt upgrade`).
  - [ ] **Restart**.
  - [ ] **(Optional)** Install essential packages.
    - [ ] git
    - [ ] make
    - [ ] g++
    - [ ] figlet
    - ...
- [ ] **(Optional)** Update motd.
  - Write following content to `/etc/update-motd.d/01-hostname` and `chmod +x`.

    ```sh
    #!/bin/sh
    figlet -f big "Server '$(hostname)'"
    ```

- [ ] SSH configuration.
  - [ ] Change sshd port (in `/etc/ssh/sshd_config`).
  - [ ] **(Optional)** Add publickey to `~/.ssh/authorized_keys`
  - [ ] Restart sshd service.
