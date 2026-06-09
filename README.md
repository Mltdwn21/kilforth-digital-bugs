# Kilforth Digital — Bug Reports

Public issue tracker for **Gloom of Kilforth Digital**, a personal fan adaptation of *Gloom of Kilforth: A Fantasy Quest Game* by Tristan Hall / Hall or Nothing Productions.

There is no source code in this repo. It exists only to collect bug reports from playtesters.

## How to file a bug

**From inside the game** (recommended — gives the most diagnostic context):

1. Press `Esc` during play to open the pause menu.
2. Click **Report Bug**.
3. Describe what happened and what you expected.
4. Click **Submit**.

The game packages the events log, current game state, and your latest autosave into a ZIP, uploads it, and opens a pre-filled issue on this repo automatically. You just confirm the title and click **Submit new issue**.

**Manually** (when the in-game flow isn't an option):

1. [Open a new issue](../../issues/new/choose) and use the Bug Report template.
2. Attach the most recent ZIP from your file manager. The in-game submit flow generates one ZIP per attempt, even if you abandon the browser step.

Bundle location:

| OS | Path |
|---|---|
| Windows | `%APPDATA%\Godot\app_userdata\Kilforth Digital\bug_reports\` |
| macOS | `~/Library/Application Support/Godot/app_userdata/Kilforth Digital/bug_reports/` |
| Linux | `~/.local/share/godot/app_userdata/Kilforth Digital/bug_reports/` |

## What's in the diagnostic bundle

| File | Contents |
|---|---|
| `bug_info.txt` | Description + system info (OS, Godot version, build version, viewport size, current game day/phase) |
| `state.json` | Full game state at submission (hero name, position, inventory, deck state) |
| `memory_timeline.csv` | Rolling memory + object-count samples for leak diagnosis |
| `logs/events_*.log` | Game events log (dialogs, phase transitions, hero actions) |
| `logs/godot*.log` | Engine output (warnings, errors, paths) |
| `save/auto_*.save` | Most recent autosave for the active playthrough |

## Privacy notes

Bug bundles become public once an issue is filed:

- The download link inside the issue body is public; anyone who finds the issue can fetch the ZIP.
- The Windows engine log contains your user folder path (i.e. your Windows username).
- Your hero name and game state are in the bundle.

Pseudonymous play is fine — give your hero a non-identifying name if you'd rather. Avoid putting personal information into the description, since it's posted to a public issue. A throwaway GitHub account is fine if you don't want your real account associated with reports.

## Build versions

The build version is shown on the main menu (bottom-right corner) and in `bug_info.txt` inside the bundle. When reporting, include the version — older bundles are still useful but knowing the build matters for reproducing.

## Notes

The main code repository is private. This repo exists only to collect bug reports — it has no source code.
