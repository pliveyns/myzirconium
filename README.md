# myzirconium &nbsp; [![bluebuild build badge](https://github.com/pliveyns/myzirconium/actions/workflows/build.yml/badge.svg)](https://github.com/pliveyns/myzirconium/actions/workflows/build.yml)

My customized Fedora Atomic image with niri TWM based on Zirconium.
See [Zirconium] for the base image.

See cwalsothe [BlueBuild docs](https://blue-build.org/how-to/setup/) for quick setup instructions for setting up your own repository.

## Installation

> [!WARNING]  
> [This is an experimental feature](https://www.fedoraproject.org/wiki/Changes/OstreeNativeContainerStable), try at your own discretion.

To rebase an existing atomic Fedora installation to the latest build:

- To rebase from some flavour of Fedora Atomic installed:
  ```
  sudo bootc switch ghcr.io/pliveyns/myzirconium
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build. That build will still always use the Fedora version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/pliveyns/myzirconium
```
