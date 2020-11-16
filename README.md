# The Ur-Quan Masters MegaMod Flatpak

A [Flatpak](https://flatpak.org/) build of [The Ur-Quan Masters MegaMod](https://github.com/Serosis/UQM-MegaMod).

## Installation

This is a work in progress. For now you'll need to build the packages yourself.

Building & installing the flatpak locally is simple - ensure flatpak-builder is installed on your system then run:

```bash
# Add the Flathub repo for the freedesktop runtime (if you haven't previously)
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
# Install the Freedesktop runtime & SDK (if you haven't previously)
flatpak install flathub org.freedesktop.Platform//20.08
flatpak install flathub org.freedesktop.Sdk//20.08
# Clone this repository
git clone https://github.com/rlac/flatpak-uqm-megamod.git
cd flatpak-uqm-megamod
# Build and install the base Ur-Quan Masters MegaMod app
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.json --force-clean
```

Optional add-ons are available as extensions. To build and install the add-on you want to use, complete the above steps and then:

```bash
# HD content
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.AddOn.HD.json --force-clean
# 3DO voices
flatpak-builder --install --user builddir com.github.serosis.UQM_MegaMod.AddOn.Voice3DO.json --force-clean
```

The 'builddir' and '.flatpak-builder' directories can be deleted from the project directory once installed.

## Running

To run the game, either use the launcher shortcut, or:

```bash
flatpak run com.github.serosis.UQM_MegaMod
```

To uninstall, run

```bash
flatpak remove com.github.serosis.UQM_MegaMod
# remove any extensions you may have installed
flatpak remove "com.github.serosis.UQM_MegaMod.AddOn.*"
```

This will also remove any installed extensions.
