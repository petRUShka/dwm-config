# dwm-6.5-custom-pkg  — Arch Linux PKGBUILD

This repo **does not fork dwm’s source**.  
It only contains a PKGBUILD that builds vanilla **dwm 6.5** plus:

* systray patch (2023-09-22)  
* 1 px inner gaps  
* personalised `config.h`

| feature                        | upstream 6.5 | this package |
|--------------------------------|--------------|--------------|
| primary **Mod** key            | **Alt**      | **Super / Win** |
| launcher / terminal            | `dmenu_run` / `st` | `rofi -show run` / `alacritty` |
| systray                        | —            | ✔ (2 px spacing) |
| inner gaps                     | 0 px         | 1 px |
| lock shortcut                  | —            | `Super + Shift + L` → `lock` |
| fonts                          | `monospace` 10 | Sans 10.5 / VL Gothic 10.5 / WenQuanYi 10.5<br>+ Terminus-16 for rofi |
| colours, layouts, rules        | stock        | **unchanged** |

---

## Build & install

```bash
git clone https://git.example.com/yourname/dwm-6.5-custom-pkg.git
cd dwm-6.5-custom-pkg
makepkg -si          # builds dwm-6.5-custom-*.pkg.tar.zst and installs it
