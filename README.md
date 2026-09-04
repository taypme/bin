# taypme/bin

Small command-line helpers for working with the taypme workspace. Most tools
are designed to be called from a checkout under `$HOME/tsync` and intentionally
wrap existing commands rather than hide their output.

## Quick reference

| Command | Purpose |
| --- | --- |
| `www [repo]` | Enter the workspace or show a repository's Git status |
| `console ...` | Run `php bin/console` through Docker Compose |
| `str FIND REPLACE` | Recursively replace UTF-8 text and filenames |
| `yeet [message]` | Commit current changes and push them |
| `reverb` | Rebase local work and amend/push the tracked tip |
| `main` | Replace the current branch history with a squashed `main` |
| `tsync_drive_down` | Copy Google Drive files into the local drive mirror |
| `tsync_drive_bisync` | Resynchronize the local mirror with Google Drive |
| `tsync_drive_dedupe` | Preview duplicate handling on Google Drive |
| `tsync_syncthing` | Mirror the tsync folder to the Syncthing folder |
| `tsync_usb` | Mirror tsync to the configured USB mount |

For a script's exact flags and side effects, read the script or run its
`--help` option when available.

## Safety

Several commands mutate remote repositories, Google Drive, or removable media.
Review the current directory, remote, mount, and dry-run output first. In
particular, `main`, `reverb`, `yeet`, `tsync_drive_bisync`, and `tsync_usb` can
change or delete data. The sync scripts exclude Git metadata; the Syncthing
mirror also excludes `node_modules/`, `vendor/`, and protects `.stfolder`.

## Utilities

The repository includes commands for console access, forensic work, file routing, Google Drive workflows, Syncthing, USB mirroring, web tasks, and related maintenance operations. Inspect each script's usage output before running it.

The scripts have no package-manager setup step. Ensure their external tools
(`git`, `rclone`, `rsync`, Docker, or Syncthing) are installed and configured
before use.
