# appimage-install

Tiny Python 3 script (no dependencies) that "installs" an AppImage: moves it to `~/Applications`, extracts its icon, and adds a start-menu entry.

## Usage

```bash
./appimage-install ~/Downloads/Obsidian-1.5.3-x86_64.AppImage   # name guessed: "Obsidian"
./appimage-install some-file.AppImage "My Cool App"             # custom name
./appimage-install --remove Obsidian                            # uninstall
./appimage-install --help
```

Tip: copy it into your PATH with `cp appimage-install ~/.local/bin/`.

## Where things go

| What          | Location                                      |
|---------------|-----------------------------------------------|
| AppImage      | `~/Applications/<Name>.AppImage`              |
| Desktop entry | `~/.local/share/applications/appimage-<Name>.desktop` |
| Icon          | `~/.local/share/icons/appimage-<Name>.png/svg` |

Change the paths at the top of the script if you prefer other locations.

> Note: extracting the icon runs the AppImage (`--appimage-extract`), so only use it on AppImages you trust.
