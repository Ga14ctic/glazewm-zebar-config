# GlazeWM + Zebar Config

My Windows 11 tiling setup — [GlazeWM](https://github.com/glzr-io/glazewm) with a [Zebar](https://github.com/glzr-io/zebar) status bar.

## What's in here

```
glazewm/config.yaml   → goes in ~/.glzr/glazewm/
zebar/settings.json   → goes in ~/.glzr/zebar/
```

## Highlights

- **Native window animations** enabled (`window_animations: "always"`)
- **Cursor jump on window focus** — the pointer follows your focus
- **10px inner gaps**, 50px top outer gap to clear the Zebar bar
- **Focused window border** in crimson `#c63b4e`, unfocused in slate `#2a3a4f`
- 9 workspaces, vim-style `alt+hjkl` focus/move bindings, `alt+r` resize mode, `alt+shift+p` pause mode
- `alt+enter` launches WezTerm — swap for `wt` if you use Windows Terminal
- Zebar runs the official `glzr-io.starter` marketplace pack with the `with-glazewm` widget

## Install

1. Install [GlazeWM and Zebar](https://github.com/glzr-io/glazewm/releases) (the GlazeWM installer can bundle Zebar).
2. Copy the files into place:

   ```powershell
   Copy-Item glazewm\config.yaml "$env:USERPROFILE\.glzr\glazewm\config.yaml"
   Copy-Item zebar\settings.json "$env:USERPROFILE\.glzr\zebar\settings.json"
   ```

3. Reload with `alt+shift+r` (or restart GlazeWM). Zebar starts automatically via `startup_commands`.

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
