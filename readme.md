<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/docs/images/TOTEM_logo_dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="/docs/images/TOTEM_logo_bright.svg">
  <img alt="TOTEM logo font" src="/docs/images/TOTEM_logo_bright.svg">
</picture>

This repository is a fork of [GEIGEIGEIST zmk-config-totem](https://github.com/GEIGEIGEIST/zmk-config-totem).
It turns it into a [ZMK module](https://zmk.dev/docs/features/modules) and
follows recommendations from the ZMK project:
> A common ZMK setup thus consists of the following separate components, commonly housed in their respective Git repositories:
> - A single ZMK config maintained by the user, containing the .conf and .keymap files for one or multiple keyboards. This is also where files from ZMK or modules should be overridden/modified, if there is a need.
> - Any number of ZMK modules, maintained by the module's owner. Some modules may contain multiple keyboards or functionalities. If all of your keyboards and functionalities are internal to ZMK's tree, then no modules are necessary.
> - The ZMK firmware itself, maintained by its contributors.

This git repository only contains the code for the TOTEM shield (read "keyboard" if you are unfamiliar with ZMK terminology).
It’s meant to be used in combination with a separate "config" repository which will contain your own keymap definitions.

Its `main` branch has the necessary changes to make it build with ZMK `main` branch.
Its `v0.3-branch` branch has the necessary changes to make it build using ZMK `v0.3-branch` branch.

Both branches also have support for ZMK Studio.

The keymap is unchanged save for a `&studio_unlock` addition.


# ZMK CONFIG FOR THE TOTEM SPLIT KEYBOARD

[Here](https://github.com/GEIGEIGEIST/totem) you can find the hardware files and build guide.\
[Here](https://github.com/GEIGEIGEIST/qmk-config-totem) you can find the QMK config for the TOTEM.

TOTEM is a 38 key column-staggered split keyboard running [ZMK](https://zmk.dev/) or [QMK](https://docs.qmk.fm/). It's meant to be used with a SEEED XIAO BLE or RP2040.


![TOTEM layout](/docs/images/TOTEM_layout.svg)



## HOW TO USE

- fork this repo
- `git clone` your repo, to create a local copy on your PC (you can use the [command line](https://www.atlassian.com/git/tutorials) or [github desktop](https://desktop.github.com/))
- adjust the totem.keymap file (find all the keycodes on [the zmk docs pages](https://zmk.dev/docs/codes/))
- `git push` your repo to your fork
- on the GitHub page of your fork navigate to "Actions"
- scroll down and unzip the `firmware.zip` archive that contains the latest firmware
- connect the left half of the TOTEM to your PC, press reset twice
- the keyboard should now appear as a mass storage device
- drag'n'drop the `totem_left-xiao_ble-zmk.uf2` file from the archive onto the storage device
- repeat this process with the right half and the `totem_right-xiao_ble-zmk.uf2` file.
