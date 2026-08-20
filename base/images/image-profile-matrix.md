# Azure Linux 4 image profile matrix

Development images are omitted. An X indicates that the profile is selected
directly or transitively by the image.

## VM images

| Profile               | vm-base    | vm-iso-installer | minimal-os | 1p-vm-base-gen1 | 1p-vm-base-gen1-fips | 1p-vm-base-gen2-fips | marketplace-gen2 | marketplace-gen2-cvm | marketplace-gen2-fips |
| --------------------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| BootableCore          | X          | X          | X          | X          | X          | X          | X          | X          | X          |
| CloudCore             | X          |            |            | X          | X          | X          | X          | X          | X          |
| RuntimeRepos          | X          | X          | X          | X          | X          | X          | X          | X          | X          |
| BootstrapRepos        | X          | X          | X          |            |            |            | X          | X          | X          |
| Fips                  |            |            |            |            | X          | X          |            |            | X          |
| UefiBoot              |            | X          |            |            |            | X          | X          |            | X          |
| LegacyBoot            |            |            |            | X          | X          |            |            |            |            |
| MinimalOsCore         |            |            | X          |            |            |            |            |            |            |
| InstallerCore         |            | X          |            |            |            |            |            |            |            |
| VmBaseCore            | X          |            |            |            |            |            |            |            |            |
| OnePBase              |            |            |            | X          | X          | X          |            |            |            |
| MarketplaceBase       |            |            |            |            |            |            | X          | X          | X          |
| vm-base               | X          |            |            |            |            |            |            |            |            |
| vm-iso-installer      |            | X          |            |            |            |            |            |            |            |
| minimal-os            |            |            | X          |            |            |            |            |            |            |
| 1p-vm-base-gen1       |            |            |            | X          |            |            |            |            |            |
| 1p-vm-base-gen1-fips  |            |            |            |            | X          |            |            |            |            |
| 1p-vm-base-gen2-fips  |            |            |            |            |            | X          |            |            |            |
| marketplace-gen2      |            |            |            |            |            |            | X          |            |            |
| marketplace-gen2-cvm  |            |            |            |            |            |            |            | X          |            |
| marketplace-gen2-fips |            |            |            |            |            |            |            |            | X          |

## Container and WSL images

| Profile            | wsl        | container-base | container-distroless-minimal | container-distroless-base | container-distroless-debug |
| ------------------ | ---------- | ---------- | ---------- | ---------- | ---------- |
| RuntimeRepos       |            | X          |            |            |            |
| BootstrapRepos     | X          | X          |            |            |            |
| ContainerCore      |            | X          |            |            |            |
| DistrolessCore     |            |            | X          | X          | X          |
| DistrolessBase     |            |            |            | X          | X          |
| WslCore            | X          |            |            |            |            |
| wsl                | X          |            |            |            |            |
| core               |            | X          |            |            |            |
| distroless-minimal |            |            | X          |            |            |
| distroless-base    |            |            |            | X          |            |
| distroless-debug   |            |            |            |            | X          |
