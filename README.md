# The Ur-Quan Masters Flatpak

A [Flatpak](https://flatpak.org/) build of [The Ur-Quan Masters MegaMod](https://github.com/Serosis/UQM-MegaMod).

## Installation

This is a work in progress. For now you'll need to build the packages yourself.

Building & installing the flatpak locally is simple - ensure flatpak-builder is installed on your system then run:

```bash
# Flathub repo for the freedesktop runtime
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Platform//18.08
flatpak install flathub org.freedesktop.Sdk//18.08
# Build and install the base app without optional add-ons
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.json --force-clean
```

Optional add-ons are available as extensions. To build and install the add-on you want to use, complete the above steps and then:

```bash
# HD content
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.AddOn.HD.json --force-clean
# 3DO voices
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.AddOn.Voice3DO.json --force-clean
```

## Running

To run the game, either use the launcher shortcut, or:

```bash
flatpak run com.github.serosis.UQM_MegaMod
```

To uninstall, run

```bash
flatapk remove com.github.serosis.UQM_MegaMod
```

This will also remove any installed extensions.