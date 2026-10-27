# Is The Thin Place VR safe to install?

The short answer is that you don't need to take anyone's word for it. This page explains what the app does and doesn't do, what you can check yourself, and the two things that tend to put people off: the Windows warning, and anti-cheat.

---

## What it is

The Thin Place VR is a tool for VR sim racing, currently in free beta. It draws flat windows inside your VR game, and Virtual Desktop fills them with your Quest 3's passthrough camera view, so you can see your real wheel, hands, keyboard or Stream Deck while you drive.

It has two parts:

- **The app** (The Thin Place VR in your Start menu), where you choose and arrange the windows.
- **A small VR add-on, called an OpenXR layer.** VR games load it to draw the windows. It's the same kind of add-on as the popular OpenXR Toolkit.

---

## What you can check yourself

**Scan it with dozens of antivirus programs.** Upload the installer to [virustotal.com](https://www.virustotal.com). It's checked by around 70 antivirus engines at once. Very occasionally one small engine flags any new, uncommon program; that's normal for software few people have downloaded yet.

**Check the file is the one published here.** Each installer on the [Releases page](https://github.com/symyoulater/Thin-Place-VR/releases) shows its SHA-256 fingerprint next to the download. To check your copy, open PowerShell in your Downloads folder and run:

```
Get-FileHash ThinPlaceVR-Setup-0.14.5.exe
```

Use the file name of the installer you downloaded. If the long code matches the one on the Releases page, the file hasn't been changed. The app's own **Check for updates** does this check for you automatically before installing anything.

**Built on GitHub's servers.** Installers are built automatically on GitHub's build servers, not on anyone's home PC.

---

## What it does on your PC

**It doesn't send any of your data anywhere.** There's no tracking, no analytics, no account and no sign-in. The only time it goes online is to check this page for a newer version. Before installing an update, it makes sure the file came from this project's releases and matches the fingerprint published for it.

**Its settings and logs stay on your PC.** Window positions are saved in **Documents\Thin Place VR**. The log of the last game session is in **C:\ProgramData\Thin Place VR**. They only leave your PC if you choose to send them to someone.

**Hotkeys.** To make the Ctrl+Alt hotkeys work inside games, the VR add-on watches the keyboard while a VR game is running. It only reacts to its own key combinations. It doesn't record or store what you type.

**Hand tracking.** To line the windows up with your real wheel, the VR add-on reads the positions of your hands from the headset's hand tracking while a VR game is running. It only uses where your palms are while you hold the wheel. It doesn't see any camera images, and nothing is recorded or sent anywhere.

**Game data windows read, they never write.** The optional AC EVO and Elite Dangerous data windows read the information those games already publish for dashboards and overlays. They don't change anything in the game.

**Web windows are walled off.** If you put a website in a window, it runs in its own separate browser space. It has no access to the app or your files, and can't use your camera or microphone. The app's own screens are locked down so they can't load anything from the internet.

**Why it asks for administrator permission.** Windows needs administrator permission for two things: installing into Program Files, and telling VR games where to find the VR add-on (one registry entry, the standard OpenXR place for this). That's all it uses admin rights for.

---

## The Windows warning

When you run the installer, Windows may show a blue box saying **"Windows protected your PC"** and **"Unknown publisher"**.

This is because the installer isn't signed with a paid code-signing certificate yet. Windows shows this warning for most small, new projects. It doesn't mean Windows found anything wrong with it.

To carry on, click **More info**, then **Run anyway**.

If you'd like to be extra careful, do the VirusTotal check above first.

---

## Anti-cheat

Because the VR add-on loads into VR games, some anti-cheat systems don't allow it:

- **Le Mans Ultimate** uses Easy Anti-Cheat, which currently stops The Thin Place VR from loading. The game still runs normally, just without the windows.
- **Other games with strict anti-cheat**, especially competitive online ones, may react the same way. We have no reports of anyone being banned, but we can't promise how every anti-cheat system will treat it.

If you play online games with strict anti-cheat and want to be completely safe, uninstall The Thin Place VR before playing them. Reinstalling takes about a minute, and your window positions are kept.

---

## Removing it

Go to **Windows Settings → Apps → Installed apps → The Thin Place VR → Uninstall**.

This removes the app and the VR add-on, including its registry entry, so games stop loading it straight away. Two folders are left behind in case you reinstall: your window positions in **Documents\Thin Place VR**, and the log in **C:\ProgramData\Thin Place VR**. Delete them if you don't want them.

---

## Questions

If something worries you, ask on the [The Thin Place VR Discord](https://discord.gg/XkukAhckz2) or open an issue on the [GitHub page](https://github.com/symyoulater/Thin-Place-VR/issues). A real person will answer.
