# Azure Linux 4 profile package tables

Each column is a profile and each cell below it is a package declared by
that profile. Package names are deduplicated across bootstrap and image
package blocks. Architecture qualifiers and package phase are omitted.

## Core profiles

### Foundational core profiles

| BootableCore     | CloudCore                | ContainerCore                | DistrolessCore               |
| ---------------- | ------------------------ | ---------------------------- | ---------------------------- |
| bash             | WALinuxAgent             | azurelinux-release-container | azurelinux-release-container |
| ca-certificates  | azurelinux-release-cloud | bash                         | busybox                      |
| dnf5             | bzip2                    | filesystem                   | filesystem                   |
| filesystem       | chrony                   |                              | tzdata                       |
| grub2            | cloud-init               |                              |                              |
| iproute          | cloud-utils-growpart     |                              |                              |
| kernel           | cracklib-dicts           |                              |                              |
| shadow-utils     | cryptsetup               |                              |                              |
| systemd          | file                     |                              |                              |
| systemd-networkd | glibc                    |                              |                              |
| systemd-resolved | glibc-langpack-en        |                              |                              |
| util-linux       | grubby                   |                              |                              |
|                  | gzip                     |                              |                              |
|                  | hyperv-daemons           |                              |                              |
|                  | iputils                  |                              |                              |
|                  | irqbalance               |                              |                              |
|                  | kernel-modules           |                              |                              |
|                  | lvm2                     |                              |                              |
|                  | lz4                      |                              |                              |
|                  | net-tools                |                              |                              |
|                  | nftables                 |                              |                              |
|                  | openssh-clients          |                              |                              |
|                  | openssh-server           |                              |                              |
|                  | selinux-policy-targeted  |                              |                              |
|                  | setup                    |                              |                              |
|                  | sudo                     |                              |                              |
|                  | tar                      |                              |                              |
|                  | wget                     |                              |                              |
|                  | which                    |                              |                              |
|                  | zlib                     |                              |                              |

### Image-family core profiles

| WslCore                 | MinimalOsCore          | InstallerCore             | VmBaseCore               |
| ----------------------- | ---------------------- | ------------------------- | ------------------------ |
| acl                     | azurelinux-release     | anaconda-core             | acl                      |
| attr                    | dbus                   | anaconda-install-env-deps | attr                     |
| azurelinux-release-wsl  | e2fsprogs              | anaconda-tui              | audit                    |
| bash                    | glibc-minimal-langpack | azurelinux-release        | azure-vm-utils           |
| bash-color-prompt       | grub2-efi-aa64         | azurelinux-rpm-config     | azurelinux-release-cloud |
| bash-completion         | grub2-efi-aa64-modules | coreutils                 | bash-completion          |
| bind-utils              | grub2-efi-x64          | cracklib-dicts            | bind-utils               |
| bzip2                   | grub2-efi-x64-modules  | createrepo_c              | brotli                   |
| coreutils               | iputils                | dracut-live               | chkconfig                |
| curl                    | irqbalance             | dracut-network            | coreutils                |
| dbus                    | ncurses-libs           | efibootmgr                | cronie                   |
| default-editor          | openssl                | glibc                     | cyrus-sasl               |
| dnf5                    | rpm                    | glibc-langpack-en         | device-mapper-event      |
| dnf5-plugins            | shim                   | hostname                  | dnf5-plugins             |
| file                    | sudo                   | hyperv-daemons            | efibootmgr               |
| glibc-langpack-en       | systemd-udev           | kernel-modules            | firewalld                |
| gnupg2                  | zlib                   | selinux-policy-targeted   | grub2-efi-aa64           |
| iproute                 |                        | setup                     | grub2-efi-aa64-modules   |
| iputils                 |                        | tar                       | grub2-efi-x64            |
| less                    |                        | vim-minimal               | grub2-efi-x64-modules    |
| lsof                    |                        |                           | hostname                 |
| man-db                  |                        |                           | man-db                   |
| man-pages               |                        |                           | nano                     |
| nmap-ncat               |                        |                           | ncurses                  |
| openssh-clients         |                        |                           | ncurses-term             |
| passwd                  |                        |                           | nvme-cli                 |
| pciutils                |                        |                           | rootfiles                |
| procps-ng               |                        |                           | rsync                    |
| rpm                     |                        |                           | shim                     |
| rsync                   |                        |                           | tpm2-tss                 |
| shadow-utils            |                        |                           | unzip                    |
| sudo                    |                        |                           | vim-minimal              |
| symlinks                |                        |                           | zchunk                   |
| systemd-networkd        |                        |                           |                          |
| systemd-resolved        |                        |                           |                          |
| systemd-udev            |                        |                           |                          |
| tar                     |                        |                           |                          |
| tcpdump                 |                        |                           |                          |
| time                    |                        |                           |                          |
| traceroute              |                        |                           |                          |
| tree                    |                        |                           |                          |
| unzip                   |                        |                           |                          |
| usbutils                |                        |                           |                          |
| util-linux              |                        |                           |                          |
| vim-minimal             |                        |                           |                          |
| wget                    |                        |                           |                          |
| which                   |                        |                           |                          |
| whois                   |                        |                           |                          |
| wsl-setup               |                        |                           |                          |
| zip                     |                        |                           |                          |
| zram-generator-defaults |                        |                           |                          |

## Base profiles

| DistrolessBase | OnePBase                          | MarketplaceBase                   |
| -------------- | --------------------------------- | --------------------------------- |
| glibc          | SymCrypt                          | SymCrypt                          |
| libgcc         | SymCrypt-OpenSSL                  | SymCrypt-OpenSSL                  |
| openssl-libs   | azurelinux-release-identity-cloud | acl                               |
| setup          | azurelinux-rpm-config             | at                                |
|                | bc                                | atop                              |
|                | cpio                              | attr                              |
|                | cronie-anacron                    | audit                             |
|                | curl                              | azure-vm-utils                    |
|                | dbus                              | azurelinux-release-identity-cloud |
|                | dhcpcd                            | azurelinux-rpm-config             |
|                | dracut                            | bash-completion                   |
|                | e2fsprogs                         | bc                                |
|                | elfutils-libelf                   | bind-utils                        |
|                | expat                             | cpio                              |
|                | filesystem                        | cronie-anacron                    |
|                | findutils                         | curl                              |
|                | gdbm                              | dbus                              |
|                | grep                              | debootstrap                       |
|                | libtool                           | dhcpcd                            |
|                | logrotate                         | dnf-plugins-core                  |
|                | ncurses-libs                      | dracut                            |
|                | openssl                           | e2fsprogs                         |
|                | pkg-config                        | efibootmgr                        |
|                | procps-ng                         | elfutils-libelf                   |
|                | python3                           | expat                             |
|                | readline                          | filesystem                        |
|                | rpm                               | findutils                         |
|                | rpm-libs                          | gdbm                              |
|                | rsyslog                           | grep                              |
|                | sed                               | hostname                          |
|                | sqlite-libs                       | iptables                          |
|                | systemd-udev                      | jemalloc                          |
|                | tdnf                              | keyutils                          |
|                | tzdata                            | libdnf                            |
|                | wireless-regdb                    | libtool                           |
|                | xz                                | libuser                           |
|                |                                   | logrotate                         |
|                |                                   | lsof                              |
|                |                                   | man-db                            |
|                |                                   | nano                              |
|                |                                   | ncurses                           |
|                |                                   | ncurses-libs                      |
|                |                                   | ncurses-term                      |
|                |                                   | newt                              |
|                |                                   | nss                               |
|                |                                   | nvme-cli                          |
|                |                                   | openssl                           |
|                |                                   | pciutils                          |
|                |                                   | pkg-config                        |
|                |                                   | procps-ng                         |
|                |                                   | python3                           |
|                |                                   | readline                          |
|                |                                   | rng-tools                         |
|                |                                   | rootfiles                         |
|                |                                   | rpm                               |
|                |                                   | rpm-libs                          |
|                |                                   | rsync                             |
|                |                                   | rsyslog                           |
|                |                                   | sed                               |
|                |                                   | sqlite-libs                       |
|                |                                   | strace                            |
|                |                                   | sysstat                           |
|                |                                   | systemd-udev                      |
|                |                                   | tcpdump                           |
|                |                                   | time                              |
|                |                                   | tmux                              |
|                |                                   | tpm2-tss                          |
|                |                                   | traceroute                        |
|                |                                   | tzdata                            |
|                |                                   | unzip                             |
|                |                                   | vim-minimal                       |
|                |                                   | wireless-regdb                    |
|                |                                   | xz                                |
|                |                                   | zchunk                            |

## Repository traits

| RuntimeRepos     | RuntimeReposDev      | BootstrapRepos   | BootstrapReposDev    |
| ---------------- | -------------------- | ---------------- | -------------------- |
| azurelinux-repos | azurelinux-repos-dev | azurelinux-repos | azurelinux-repos-dev |

## Boot and security traits

| Fips        | UefiBoot               | LegacyBoot       |
| ----------- | ---------------------- | ---------------- |
| dracut-fips | grub2-efi-aa64         | grub2-pc         |
|             | grub2-efi-aa64-modules | grub2-pc-modules |
|             | grub2-efi-x64          |                  |
|             | grub2-efi-x64-modules  |                  |
|             | shim                   |                  |

## General VM leaf profiles

| vm-base | vm-base-dev | vm-iso-installer | vm-iso-installer-dev | minimal-os | minimal-os-dev |
| ------- | ----------- | ---------------- | -------------------- | ---------- | -------------- |
| (none)  | (none)      | (none)           | (none)               | (none)     | (none)         |

## 1P VM leaf profiles

| 1p-vm-base-gen1 | 1p-vm-base-gen1-fips | 1p-vm-base-gen2-fips |
| --------------- | -------------------- | -------------------- |
| (none)          | (none)               | efibootmgr           |

## Marketplace leaf profiles

| marketplace-gen2 | marketplace-gen2-dev | marketplace-gen2-cvm  | marketplace-gen2-cvm-dev | marketplace-gen2-fips | marketplace-gen2-fips-dev |
| ---------------- | -------------------- | --------------------- | ------------------------ | --------------------- | ------------------------- |
| (none)           | (none)               | grub2-efi-x64         | grub2-efi-x64            | (none)                | (none)                    |
|                  |                      | grub2-efi-x64-modules | grub2-efi-x64-modules    |                       |                           |
|                  |                      | shim                  | shim                     |                       |                           |
|                  |                      | tpm2-tools            | tpm2-tools               |                       |                           |

## WSL leaf profiles

| wsl    | wsl-dev |
| ------ | ------- |
| (none) | (none)  |

## Container leaf profiles

| core   | core-dev | distroless-minimal | distroless-base | distroless-debug |
| ------ | -------- | ------------------ | --------------- | ---------------- |
| (none) | (none)   | (none)             | (none)          | busybox          |
