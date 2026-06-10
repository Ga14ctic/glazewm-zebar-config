# Hiyuki — GlazeWM + Zebar Theme

A Windows 11 tiling setup themed **Hiyuki** — cold midnight blue with a crimson signal accent. [GlazeWM](https://github.com/glzr-io/glazewm) for tiling, [Zebar](https://github.com/glzr-io/zebar) for the status bar.

## Palette

| Role | Hex | |
|---|---|---|
| Background | `#0c1623` | cold midnight |
| Background (alt / elevated) | `#14202f` / `#1d2c3f` | |
| Foreground | `#e8eef5` | frost white |
| Foreground (dim) | `#919cab` | |
| Hairline / unfocused border | `#2a3a4f` | slate |
| Accent / focused border | `#c63b4e` | crimson |
| Accent (dim) | `#8a2c39` | |

## What's in here

```
glazewm/config.yaml   → ~/.glzr/glazewm/config.yaml
zebar/settings.json   → ~/.glzr/zebar/settings.json
zebar/styles.css      → %APPDATA%\Zebar\downloads\glzr-io.starter@0.0.0\styles.css
```

The Zebar bar is the official `glzr-io.starter` pack (`with-glazewm` widget) restyled by the CSS block at the bottom of `styles.css`: JetBrains Mono, frosted-glass blur over the midnight base, crimson workspace pills with a soft glow on focus, and a crimson hairline under the bar.

## Install

1. Install [GlazeWM and Zebar](https://github.com/glzr-io/glazewm/releases) (the GlazeWM installer can bundle Zebar).
2. Launch Zebar once so it downloads the `glzr-io.starter` pack.
3. Copy the files into place:

   ```powershell
   Copy-Item glazewm\config.yaml "$env:USERPROFILE\.glzr\glazewm\config.yaml"
   Copy-Item zebar\settings.json "$env:USERPROFILE\.glzr\zebar\settings.json"
   $pack = Get-ChildItem "$env:APPDATA\Zebar\downloads" -Directory -Filter "glzr-io.starter@*" | Select-Object -First 1
   Copy-Item zebar\styles.css "$($pack.FullName)\styles.css"
   ```

4. Reload GlazeWM with `alt+shift+r` and restart Zebar (tray icon → Reload). Zebar starts automatically with GlazeWM via `startup_commands`.

> If your starter pack version differs from `0.0.0`, only the theme block matters — copy everything from `/* === SWITCHYARD THEME === */` to `/* === END SWITCHYARD === */` onto the end of your pack's `styles.css`.

## GlazeWM highlights

- **Native window animations** enabled (`window_animations: "always"`)
- **Cursor jump on window focus** — the pointer follows your focus
- **10px inner gaps**, 50px top outer gap to clear the Zebar bar
- Focused window border in crimson `#c63b4e`, unfocused in slate `#2a3a4f`
- 9 workspaces, vim-style `alt+hjkl` focus/move bindings, `alt+r` resize mode, `alt+shift+p` pause mode
- `alt+enter` launches WezTerm — swap for `wt` if you use Windows Terminal

## Key bindings cheat sheet

| Binding | Action |
|---|---|
| `alt+h/j/k/l` or arrows | Focus left/down/up/right |
| `alt+shift+h/j/k/l` | Move window |
| `alt+1..9` | Focus workspace |
| `alt+shift+1..9` | Move window to workspace |
| `alt+a` / `alt+s` / `alt+d` | Prev / next / recent workspace |
| `alt+r` | Resize mode (hjkl/arrows, esc to exit) |
| `alt+v` | Toggle tiling direction |
| `alt+t` / `alt+shift+space` / `alt+f` | Tiling / floating / fullscreen |
| `alt+m` | Minimise |
| `alt+shift+q` | Close window |
| `alt+enter` | Launch terminal |
| `alt+shift+r` | Reload config |
| `alt+shift+p` | Pause all keybindings |
| `alt+shift+e` | Exit GlazeWM |
