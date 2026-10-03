# Download Loopcast

> This repository only hosts Loopcast's installers and update files. The source code is private.

**Get the latest version:** https://github.com/crystallyons89-ai/loopcast-releases/releases/latest

Pick the file for your computer under **Assets**:

| Your computer | File to download |
| --- | --- |
| Windows 10 / 11 | `Loopcast_x.y.z_x64-setup.exe` (recommended) or `Loopcast_x.y.z_x64_en-US.msi` |
| Mac (Apple Silicon or Intel) | `Loopcast_x.y.z_universal.dmg` |
| Linux (x86-64) | `Loopcast_x.y.z_amd64.AppImage` |

Ignore the `.sig`, `.tar.gz` and `latest.json` files — those are for automatic updates.

Once installed, **Loopcast updates itself**. It checks every few hours; if the window is
closed (bot running in the tray) it installs the update and restarts quietly, otherwise a
**Restart to update** button appears at the bottom of the sidebar.

---

## Windows

1. Download `Loopcast_x.y.z_x64-setup.exe` and open it.
2. **If you see "Windows protected your PC"** (SmartScreen): click **More info**, then
   **Run anyway**. This appears because Loopcast is new and not yet code-signed; it does not
   mean the file is harmful.
3. Follow the installer. No administrator rights are needed — Loopcast installs for your
   account only and adds a **desktop shortcut** and a **Start Menu** entry.
4. Loopcast opens on the setup screen.

Prefer an `.msi` (for managed / company PCs)? It installs for all users and asks for
administrator rights. The `.exe` is the better choice for most people.

**Running in the background:** closing the window keeps the bot running in the system tray
(bottom-right, near the clock — you may need to click **^** to see it). Right-click the
icon → **Quit Loopcast** to stop it. **Open at login** is on by default; switch it off in
**Settings**.

**Uninstall:** Settings → Apps → Installed apps → Loopcast → Uninstall.

## Mac

1. Download `Loopcast_x.y.z_universal.dmg` (works on Apple Silicon and Intel Macs).
2. Open it and drag **Loopcast** into **Applications**.
3. Open Loopcast from Applications. Because it is not yet notarized by Apple, macOS will
   block the first launch. To allow it:
   - **macOS 15 Sequoia and later:** you'll see *"Loopcast" Not Opened* → click **Done**.
     Open **System Settings → Privacy & Security**, scroll down to *"Loopcast" was blocked*
     and click **Open Anyway**, then confirm with your password.
   - **macOS 14 and earlier:** right-click (or Control-click) Loopcast in Applications →
     **Open** → **Open**.
   - **If macOS says "Loopcast is damaged and can't be opened"**, open **Terminal** and run:
     ```sh
     xattr -dr com.apple.quarantine /Applications/Loopcast.app
     ```
     then open it again. (This removes the "downloaded from the internet" flag; it is
     needed only once.)
4. **Keep it in the Dock:** while Loopcast is open, right-click its Dock icon →
   **Options → Keep in Dock**.

Closing the window keeps the bot running; use the Loopcast icon in the menu bar → **Quit
Loopcast** to stop it. **Uninstall:** quit Loopcast and drag it from Applications to the Bin.

## Linux

1. Download `Loopcast_x.y.z_amd64.AppImage`.
2. Make it executable and run it:
   ```sh
   chmod +x Loopcast_*_amd64.AppImage
   ./Loopcast_*_amd64.AppImage
   ```
   Or in your file manager: right-click → Properties → Permissions → *Allow executing as a
   program*, then double-click.
3. If it doesn't start and mentions **FUSE**, install it:
   `sudo apt install libfuse2` (Ubuntu 22.04) or `sudo apt install libfuse2t64` (Ubuntu 24.04+).
4. Loopcast stores your account sign-ins in your desktop's keyring (GNOME Keyring or
   KWallet). Most desktops have one already.

Keep the AppImage somewhere you can write to (e.g. `~/Applications`) so it can update itself.

---

## Your accounts and privacy

Loopcast runs entirely on your computer. During setup **you sign in with your own**
YouTube, X, TikTok and Instagram accounts; the sign-in tokens are stored in your
computer's own keychain (Windows Credential Manager, macOS Keychain, or the Linux keyring)
and never leave your machine. Loopcast does not include anyone else's accounts or keys.
Your videos, schedule and queue are stored locally too.

> **Current status:** account connections in setup are still placeholders — real
> sign-in for each platform is coming in a later version. Uploads and posts are simulated
> until then; nothing is published to your accounts.
