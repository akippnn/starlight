# starlight

> [!warning]
> Currently in unstable phase. Do not use in production.

[![build-starlight](https://github.com/akippnn/starlight/actions/workflows/build.yml/badge.svg)](https://github.com/ublue-os/startingpoint/actions/workflows/build.yml)

You lay in a clear field, feeling the midnight breeze as you stare into the starlight.

"starlight" is a custom image based on [ublue-os/startingpoint](https://github.com/ublue-os/startingpoint). The entire mechanism (build/release-iso workflows + recipe.yml parser + modules) belongs to them. "starlight" is simply a biased pre-configured system with all the basic necessities needed for a presentable and usable wlr-based system.

For more info, check out the [uBlue homepage](https://universal-blue.org/) and the [main uBlue repo](https://github.com/ublue-os/main/)

## Getting started

> [!warning] For Ventoy users
>
> There is a known issue with Ventoy at [ublue-os/main #108](https://github.com/ublue-os/main/issues/108). In the meantime, please use an alternative method to create bootable drives.


If you do not currently use an Fedora OSTree system, create a bootable drive using the ISO from the [releases page](https://github.com/akippnn/starlight/releases) and then boot to it.

## Existing OSTree installation

To rebase an existing installation to the latest build:

- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  sudo rpm-ostree rebase ostree-unverified-registry:ghcr.io/akippnn/starlight:latest
  systemctl reboot
  ```

- Then rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/akippnn/starlight:latest
  systemctl reboot
  ```

Available tags:
- `latest`
- `39`
- This repository builds date tags as well, so if you want to rebase to a particular day's build:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/ublue-os/startingpoint:20230403
  ```

## Configuration

- **Hyprland**  
  `starlight` modifies `/usr/share/wayland-sessions/hyprland.desktop` to run Hyprland using `Hyprland -c /etc/hyprland.conf`. To configure Hyprland, please modify `/etc/hyprland.conf` instead.
