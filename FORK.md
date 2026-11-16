# This fork

A fork of [foot-macos](https://github.com/gobijan/foot-macos), reduced to
what upstream foot has on Linux. It starts from the original port commit
(`9ad30d3c`), merges current upstream foot, and keeps only a few later
fixes.

Removed from the port:

- Persistent sessions (`footd`, `macos-session*`, snapshots, remote
  sessions, connections, login prompts, `Quit and End Sessions`)
- Automatic shell integration scripts (`macos-shell-integration`)
- Remote control and `foot @` (`macos/control*`)
- The command palette (`macos/palette.m`)
- The Quake terminal and its global hotkey (`macos/quake.m`, `macos/hotkey.m`)
- Native tabs and splits (`macos/tabs.m`, `macos/split*`, `macos/splits*`)
- The port's custom titlebar styles
- Notification Center integration and command-finished notifications
- Close confirmation (`macos-confirm-close`)
- Hints, Cmd+click URL opening, the pager, custom titles, and input to all
  splits
- Secure Keyboard Entry, VoiceOver support, and the Settings/Theme/Updates
  menus
- macOS defaults: login shell, 8pt padding, Grok colors, font smoothing,
  and following the system appearance

Kept:

- One terminal per window, as upstream
- The native AppKit/CoreText/CoreAnimation platform layer
- foot's terminal core, scrollback, search, URL mode, IME, clipboard,
  color themes from `include=`
- `macos-option-as-alt` (Option has to map to Alt/Meta somehow)
- `[csd] preferred=none`: Alacritty's buttonless titlebar (no title or
  traffic lights, terminal under it); close it with `Cmd+W`
- The `Edit foot.ini…` menu item, which opens `~/.config/foot/foot.ini`

Build and test as before: `make build`, `make test`, `make run`.
