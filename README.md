# dwm-6.5-custom-pkg  — Arch Linux PKGBUILD

This repo **does not fork dwm’s source**.  
It only contains a PKGBUILD that builds vanilla **[dwm](http://dwm.suckless.org/) 6.5** plus:

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
```

## Default key-bindings

| Keys | Action |
|------|--------|
| **Alt&nbsp;+&nbsp;F2** | Launch **rofi** run menu |
| **Alt&nbsp;+&nbsp;F1** | Launch **alacritty** terminal |
| **Super&nbsp;+&nbsp;b** | Toggle status bar |
| **Super&nbsp;+&nbsp;j / k** | Focus next / previous client |
| **Super&nbsp;+&nbsp;h / l** | Shrink / grow master area |
| **Super&nbsp;+&nbsp;Return** | Zoom / swap focused client |
| **Super&nbsp;+&nbsp;c** | Kill focused window |
| **Super&nbsp;+&nbsp;t** | Tiled layout |
| **Super&nbsp;+&nbsp;Shift&nbsp;+&nbsp;f** | Floating layout |
| **Super&nbsp;+&nbsp;f** | Monocle layout |
| **Super&nbsp;+&nbsp;Shift&nbsp;+&nbsp;L** | Run `lock` (slock / i3lock) |
| **Super&nbsp;+&nbsp;1 … 9** | View tag *n* |
| **Super&nbsp;+&nbsp;Shift&nbsp;+&nbsp;1 … 9** | Move window to tag *n* |
