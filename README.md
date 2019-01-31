# The Ur-Quan Masters Flatpak

A [Flatpak](https://flatpak.org/) build of [The Ur-Quan Masters MegaMod](https://github.com/Serosis/UQM-MegaMod).

## Installation

This is a work in progress. For now you'll need to build the package yourself.

Building & installing the flatpak locally is simple - ensure flatpak-builder is installed on your system then run:

```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Sdk//18.08
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.json --force-clean
```

## Running

To run the game, either use the launcher shortcut, or:

```bash
flatpak run com.github.serosis.UQM_MegaMod
```

The package currently includes the game content and basic optional add-ons.