# Pippy Flatpak

Pippy allows the student to examine, execute, and modify simple Python programs. In addition it is possible to write Python statements to play sounds, calculate expressions, or make simple text based interactive games.

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.Pippy.git
cd org.sugarlabs.Pippy
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.Pippy.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.Pippy
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.Pippy.json
```