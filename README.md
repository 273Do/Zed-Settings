# Zed Settings

273* configuration files for the [Zed](https://zed.dev) editor.

## Preview

<img width="1746" height="1275" alt="スクリーンショット 2026-06-13 23 01 44" src="https://github.com/user-attachments/assets/952dc35b-2533-46a2-a8ef-7cff0cded14e" />

## Files

| File | Description |
|------|-------------|
| `settings.json` | Main editor settings |
| `keymap.json` | Custom key bindings |
| `tasks.json` | Custom task definitions |

---

## settings.json

### UI & Layout

| Setting | Value |
|---------|-------|
| `cli_default_open_behavior` | `new_window` — CLI always opens a new window |
| `ui_font_size` | `16` |
| `base_keymap` | `VSCode` |
| `minimap` | Disabled |
| `status_bar` | Language button, cursor position, and encoding indicator hidden |

### Panels

All panels are docked to the **left** with their toolbar buttons hidden to keep the UI minimal.

| Panel | Notes |
|-------|-------|
| Outline | button hidden |
| Collaboration | button hidden |
| Debugger | button hidden |
| Git | button hidden, `sort_by_path: true` |
| Project | button hidden, `auto_fold_dirs: false` |

### Theme

| Mode | Light | Dark |
|------|-------|------|
| Icons | Material Icon Theme | Material Icon Theme |
| UI | Ayu Light | VSCode Dark Modern |

### Theme Overrides (Transparent / Blurred)

`background.appearance` is set to `blurred` with semi-transparent RGBA values across all major surfaces, giving a frosted-glass effect over the desktop wallpaper.

Key overrides:
- `background`: `#00000060`
- `editor.background`: `#00000035`
- `tab_bar.background`: `#00000035`
- `terminal.background`: `#00000000` (fully transparent)
- `status_bar.background` / `title_bar.background`: `#00000080`

### Editor

| Setting | Value |
|---------|-------|
| Font family | `Menlo` (fallbacks: Monaco → Courier New → monospace) |
| Font size | `12` |
| Tab size | `2` |
| Show whitespaces | `boundary` |
| Indent guides | Enabled, indent-aware coloring, active line width `2` |
| Tab bar | File icons and git status enabled |
| Inlay hints | Fully enabled (parameter, value, type, and other hints) |
| Inline diagnostics | Enabled |
| Search button | Hidden |

### Terminal

| Setting | Value |
|---------|-------|
| Font family | `MesloLGS NF` (Powerline/Nerd Font patched Meslo) |
| Button | Hidden |

### AI / Agent

| Setting | Value |
|---------|-------|
| `disable_ai` | `false` |
| Agent dock | `right`, flexible layout |
| Agent server | `claude-acp` (registry type) |

### LSP & Session

- **Global LSP button** hidden from the status bar.
- **Session** — `trust_all_worktrees: true` for seamless multi-root workspace support.
- **Wakatime** — configured via `lsp` settings (replace `"API KEY HERE"` with your actual key).

### Auto-installed Extensions

These extensions are installed automatically on first launch:

- `dockerfile`
- `docker-compose`
- `glsl`
- `git-firefly`
- `html`
- `material-icon-theme`
- `python-autodoc-lsp`
- `vscode-dark-modern`
- `wakatime`

---

## keymap.json

| Binding | Context | Action |
|---------|---------|--------|
| `cmd-g` | Global | Toggle Git panel |
| `cmd-e` | Global | Toggle Project panel |
| `shift-enter` | Terminal | Send `ESC + Enter` (insert a literal newline without submitting the command) |

---

## tasks.json

### Example Task (default template)

A placeholder task demonstrating available task configuration options such as `use_new_terminal`, `allow_concurrent_runs`, `reveal`, `hide`, `shell`, and `save`.

### GLSL Viewer

Runs `glslViewer` on the currently open file. Useful for live-previewing GLSL shaders.

```json
{
  "label": "Open glsl view",
  "command": "glslViewer $ZED_FILE",
  "hide": "always",
  "allow_concurrent_runs": false,
  "use_new_terminal": true
}
```

Requires [`glslViewer`](https://github.com/patriciogonzalezvivo/glslViewer) to be installed and available on `$PATH`.
