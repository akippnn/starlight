# starlight

> [!warning]
> Currently in unstable phase. Do not use in production.

[![build-starlight](https://github.com/akippnn/starlight/actions/workflows/build.yml/badge.svg)](https://github.com/ublue-os/startingpoint/actions/workflows/build.yml)

You lay in a clear field, feeling the midnight breeze as you stare into the starlight.

"starlight" is a custom operating system based on Universal Blue's `startingpoint`. "starlight" is simply a biased preconfigured system meant to be presentable and usable. More coming soon.

For more info about Universal Blue, check out <https://universal-blue.org/> and their main repository at <https://github.com/ublue-os/main/>.

## Unstable phase

Right now, there are 

- [ ] bar (indicators/media/tray)
- [ ] wallpaper
- [ ] volume/backlight
- [ ] notification center
- [ ] idle lockscreen
- [ ] polish

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
  To configure Hyprland, please modify `/etc/hyprland.conf` instead. To reset, copy the file from `/usr/etc/hyprland.conf`.
