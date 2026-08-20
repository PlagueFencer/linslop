Azure Linux 4 image profile matrix

Development images are omitted. An X indicates that the profile is selected
directly or transitively by the image.

| Profile               | vm-base    | vm-iso-    | minimal-os | 1p-vm-     | 1p-vm-     | 1p-vm-     | marketplac | marketplac | marketplac | wsl        | container- | container- | container- | container- |
|                       |            | installer  |            | base-gen1  | base-      | base-      | e-gen2     | e-gen2-cvm | e-         |            | base       | distroless | distroless | distroless |
|                       |            |            |            |            | gen1-fips  | gen2-fips  |            |            | gen2-fips  |            |            | -minimal   | -base      | -debug     |
| --------------------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| BootableCore          | X          | X          | X          | X          | X          | X          | X          | X          | X          |            |            |            |            |            |
| CloudCore             | X          |            |            | X          | X          | X          | X          | X          | X          |            |            |            |            |            |
| RuntimeRepos          | X          | X          | X          | X          | X          | X          | X          | X          | X          |            | X          |            |            |            |
| BootstrapRepos        | X          | X          | X          |            |            |            | X          | X          | X          | X          | X          |            |            |            |
| Fips                  |            |            |            |            | X          | X          |            |            | X          |            |            |            |            |            |
| UefiBoot              |            | X          |            |            |            | X          | X          |            | X          |            |            |            |            |            |
| LegacyBoot            |            |            |            | X          | X          |            |            |            |            |            |            |            |            |            |
| ContainerCore         |            |            |            |            |            |            |            |            |            |            | X          |            |            |            |
| DistrolessCore        |            |            |            |            |            |            |            |            |            |            |            | X          | X          | X          |
| DistrolessBase        |            |            |            |            |            |            |            |            |            |            |            |            | X          | X          |
| WslCore               |            |            |            |            |            |            |            |            |            | X          |            |            |            |            |
| MinimalOsCore         |            |            | X          |            |            |            |            |            |            |            |            |            |            |            |
| InstallerCore         |            | X          |            |            |            |            |            |            |            |            |            |            |            |            |
| VmBaseCore            | X          |            |            |            |            |            |            |            |            |            |            |            |            |            |
| OnePBase              |            |            |            | X          | X          | X          |            |            |            |            |            |            |            |            |
| MarketplaceBase       |            |            |            |            |            |            | X          | X          | X          |            |            |            |            |            |
| --------------------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| vm-base               | X          |            |            |            |            |            |            |            |            |            |            |            |            |            |
| vm-iso-installer      |            | X          |            |            |            |            |            |            |            |            |            |            |            |            |
| minimal-os            |            |            | X          |            |            |            |            |            |            |            |            |            |            |            |
| 1p-vm-base-gen1       |            |            |            | X          |            |            |            |            |            |            |            |            |            |            |
| 1p-vm-base-gen1-fips  |            |            |            |            | X          |            |            |            |            |            |            |            |            |            |
| 1p-vm-base-gen2-fips  |            |            |            |            |            | X          |            |            |            |            |            |            |            |            |
| marketplace-gen2      |            |            |            |            |            |            | X          |            |            |            |            |            |            |            |
| marketplace-gen2-cvm  |            |            |            |            |            |            |            | X          |            |            |            |            |            |            |
| marketplace-gen2-fips |            |            |            |            |            |            |            |            | X          |            |            |            |            |            |
| wsl                   |            |            |            |            |            |            |            |            |            | X          |            |            |            |            |
| core                  |            |            |            |            |            |            |            |            |            |            | X          |            |            |            |
| distroless-minimal    |            |            |            |            |            |            |            |            |            |            |            | X          |            |            |
| distroless-base       |            |            |            |            |            |            |            |            |            |            |            |            | X          |            |
| distroless-debug      |            |            |            |            |            |            |            |            |            |            |            |            |            | X          |
