# Matter releases

Matter is a local Markdown workspace for notes, folders, attachments and interactive Folder Widgets. This repository hosts the official Windows installers, update metadata and release notes. Application source is maintained separately in a private repository.

## Download

The latest stable version is **Matter 0.1.8** for Windows x64.

- [Download Matter-Setup-0.1.8.exe](https://github.com/Rodjon147/matter-releases/releases/download/v0.1.8/Matter-Setup-0.1.8.exe)
- [Release notes and verification files](https://github.com/Rodjon147/matter-releases/releases/tag/v0.1.8)
- [All releases](https://github.com/Rodjon147/matter-releases/releases)

The Windows installer is currently unsigned. Windows SmartScreen may display a warning.

## What's new in 0.1.8

- **Resizable photos.** Drag an image's corner to resize it while preserving its aspect ratio. Selection borders follow the actual image, including low-resolution photos.
- **Reliable image dragging.** Drag a photo or its handle to move the complete image. Photos and incoming files cannot be dropped into a widget section, including gaps between cards.
- **Text wrapping.** Choose Full width, Wrap left, Wrap right or Original size from the image controls. Sizes and placement are saved in Markdown and restored after restarting Matter.
- **Automatic attachment cleanup.** Removing the last reference to an image or document removes its copy from workspace assets after the note saves successfully. Files used by other notes, Home or restorable trashed notes are retained; original files outside assets are untouched.
- **Undo support.** Removed attachments can be restored from a temporary recovery cache outside the workspace. Recovery copies expire after 24 hours and are cleaned at workspace startup and hourly while Matter runs.
- **Added regression coverage.** All 48 unit tests and the packaged Electron checks passed, including native image resizing/dragging, text wrapping, widget-section restrictions, attachment deletion, Undo and restart persistence.

## What's new in 0.1.7

- **Instant sidebar resizing.** The sidebar and document follow the pointer immediately while dragging the divider. Smooth collapse and expand animations are preserved.
- **Reliable divider dragging.** Pointer capture keeps resizing active outside the narrow handle and ends it when the gesture is released or cancelled.
- **Deleted notes close automatically.** Deleting an open note closes its tab and selects a neighbouring tab or Home. Deleting a folder closes all of its open notes. Deletions outside Matter are handled too.
- **Navigation stays current.** Deleted paths are removed from Back history, closed-tab history and cached documents. Pending autosave is cancelled, and late reads or saves cannot bring a deleted document back or overwrite a new note at the same path.
- **Improved installer packaging.** Main/preload source maps are excluded from the installer. Automated checks verify the packaged application version and the absence of those maps.
- **Added regression checks.** Validation includes 32 unit tests and Electron checks for sidebar resizing, deletion, navigation, saving and restart persistence.

## Updates and workspaces

Automatic updates are supported by installed Windows NSIS builds. A downloaded update is installed only after you choose **Restart & Update** and pending changes are saved. Ordinary closing does not install an update.

Updates retain your Markdown notes, attachments, Homepage, widgets and settings in their existing workspace folders. You can also install the latest Windows setup manually. Portable builds, development builds, macOS and Linux do not use this automatic update channel.

Each release includes the installer, its blockmap, `latest.yml`, `release-manifest.json` and `SHA256SUMS.txt` for integrity verification.
