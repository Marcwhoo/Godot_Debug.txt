# Godot Debug Logger

A Godot 4 addon that writes **all** debug output (print, push_error, push_warning, engine errors) to a text file in your project folder. No code changes required – it intercepts output via `OS.add_logger()`.

## Features

- **Automatic capture**: All `print()`, `push_error()`, `push_warning()` and engine messages go to file
- **Project folder**: Logs are written to `project/debugger/godot_debug.txt` (visible in editor, version control)
- **Editor Run**: Works when playing in editor – no need to check the Output panel
- **Exported builds**: Runtime logger captures output from exported games
- **No API replacement**: Keep using `print()` – no need to switch to a custom logging API

## Installation

1. Copy the `addons/godot_debug_logger` folder into your Godot project's `addons` folder
2. Enable the plugin: **Project → Project Settings → Plugins** → enable "Godot Debug Logger"
3. Add the runtime logger as Autoload: **Project → Project Settings → Autoload**
   - Path: `res://addons/godot_debug_logger/runtime_logger.gd`
   - Name: `GodotDebugLogger` (or any name you prefer)

## Output Location

Logs are written to: `your_project/debugger/godot_debug.txt`

The folder is created automatically. Add `debugger/` to `.gitignore` if you don't want logs in version control.

## Optional: Manual Logging

You can write directly to the log file from code:

```gdscript
GodotDebugLogger.log("Custom message")
# or
GodotDebugLogger.log_line("Another message")
```

## Requirements

- Godot 4.x

## License

MIT License – see LICENSE file.
