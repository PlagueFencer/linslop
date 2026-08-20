# Azure Linux 4 KIWI image hierarchy

`AzureLinux.kiwi` is the shared entry point for all Azure Linux 4 images.
The image registry selects one leaf profile for each image.

The entry point uses non-nested KIWI includes:

- `profiles/profiles.xml` defines leaf profiles and their inheritance.
- `profiles/config.xml` contains profile-scoped preferences and repositories.
- `profiles/packages.xml` contains package groups and the installer user.

## Package hierarchy

The package profiles are layered from broad to specific:

```text
BootableCore
└── CloudCore
    ├── VmBaseCore
    ├── OnePBase
    └── MarketplaceBase

ContainerCore
DistrolessCore
└── DistrolessBase

WslCore
MinimalOsCore -> BootableCore
InstallerCore -> BootableCore
```

### Core and base naming

`Core` identifies a foundational package set shared across a broad image
category. Core profiles contain the smallest common layer at that level of the
hierarchy, such as `BootableCore`, `CloudCore`, or `DistrolessCore`.

`Base` identifies the common baseline for a narrower family of sibling images.
Base profiles build on an applicable core and contain packages shared by every
variant in that family, such as `OnePBase`, `MarketplaceBase`, or
`DistrolessBase`.

These names are project conventions, not KIWI language features. KIWI treats
core and base profiles as ordinary profiles. In `VmBaseCore`, `vm-base` is the
image family name and `Core` still describes the profile's role.

## Image composition

The table lists each selected leaf profile and its full transitive profile
composition:

| Image | Profiles |
| --- | --- |
| `vm-base` | `RuntimeRepos`, `BootstrapRepos`, `BootableCore`, `CloudCore`, `VmBaseCore`, `vm-base` |
| `vm-base-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `BootableCore`, `CloudCore`, `VmBaseCore`, `vm-base-dev` |
| `container-base` | `RuntimeRepos`, `BootstrapRepos`, `ContainerCore`, `core` |
| `container-base-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `ContainerCore`, `core-dev` |
| `container-distroless-minimal` | `DistrolessCore`, `distroless-minimal` |
| `container-distroless-base` | `DistrolessCore`, `DistrolessBase`, `distroless-base` |
| `container-distroless-debug` | `DistrolessCore`, `DistrolessBase`, `distroless-debug` |
| `wsl` | `BootstrapRepos`, `WslCore`, `wsl` |
| `wsl-dev` | `BootstrapReposDev`, `WslCore`, `wsl-dev` |
| `vm-iso-installer` | `RuntimeRepos`, `BootstrapRepos`, `UefiBoot`, `BootableCore`, `InstallerCore`, `vm-iso-installer` |
| `vm-iso-installer-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `UefiBoot`, `BootableCore`, `InstallerCore`, `vm-iso-installer-dev` |
| `minimal-os` | `RuntimeRepos`, `BootstrapRepos`, `BootableCore`, `MinimalOsCore`, `minimal-os` |
| `minimal-os-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `BootableCore`, `MinimalOsCore`, `minimal-os-dev` |
| `1p-vm-base-gen1` | `RuntimeRepos`, `LegacyBoot`, `BootableCore`, `CloudCore`, `OnePBase`, `1p-vm-base-gen1` |
| `1p-vm-base-gen1-fips` | `RuntimeRepos`, `Fips`, `LegacyBoot`, `BootableCore`, `CloudCore`, `OnePBase`, `1p-vm-base-gen1-fips` |
| `1p-vm-base-gen2-fips` | `RuntimeRepos`, `Fips`, `UefiBoot`, `BootableCore`, `CloudCore`, `OnePBase`, `1p-vm-base-gen2-fips` |
| `marketplace-gen2` | `RuntimeRepos`, `BootstrapRepos`, `UefiBoot`, `BootableCore`, `CloudCore`, `MarketplaceBase`, `marketplace-gen2` |
| `marketplace-gen2-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `UefiBoot`, `BootableCore`, `CloudCore`, `MarketplaceBase`, `marketplace-gen2-dev` |
| `marketplace-gen2-cvm` | `RuntimeRepos`, `BootstrapRepos`, `BootableCore`, `CloudCore`, `MarketplaceBase`, `marketplace-gen2-cvm` |
| `marketplace-gen2-cvm-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `BootableCore`, `CloudCore`, `MarketplaceBase`, `marketplace-gen2-cvm-dev` |
| `marketplace-gen2-fips` | `RuntimeRepos`, `BootstrapRepos`, `Fips`, `UefiBoot`, `BootableCore`, `CloudCore`, `MarketplaceBase`, `marketplace-gen2-fips` |
| `marketplace-gen2-fips-dev` | `RuntimeReposDev`, `BootstrapReposDev`, `Fips`, `UefiBoot`, `BootableCore`, `CloudCore`, `MarketplaceBase`, `marketplace-gen2-fips-dev` |

Orthogonal profiles add reusable traits:

- `RuntimeRepos` / `RuntimeReposDev`
- `BootstrapRepos` / `BootstrapReposDev`
- `UefiBoot`
- `LegacyBoot`
- `Fips`

Leaf profiles should contain only packages unique to that image. Most leaves
currently contain no direct package declarations. The exceptions are the
distroless debug utility, Gen2 `efibootmgr`, and the CVM-specific boot stack.
