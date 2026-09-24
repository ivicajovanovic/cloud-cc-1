# Landing page: structure and copy (draft 2, expanded)

**Working name:** *Distro Desk*. This is a placeholder.
**What the site is:** an independent, fact-checked guide to Linux in 2026: what changed, which distros matter, and how to switch.
**Main visitor action:** find a distro that fits → go to its official download page.
**Secondary actions:** understand the options (compare, desktops, apps, gaming) → follow the switching guide.
**Voice:** plain, specific, friendly to newcomers but accurate for experts. No hype, no invented numbers, no fake testimonials. Every fact comes from `research/distros-2026.md` (the section is noted as *[R§n]*).

**Page format:** one long page with a **sticky section index** (a raised "control strip" that shows the current section). Deep content (full distro profiles, FAQ answers, glossary) sits in **expandable panels**, so the page stays scannable but still has depth.

**Creative concept, "the desk":** a physical control desk made of the soft material from `design.md`. Distros are **keycaps**, the finder uses **switches**, the release calendar is a **slider**. Data-heavy parts (comparison table, app table) stay **flat** on the surface for readability, as `design.md` §1 and §6 require.

---

## Page map (18 sections)

| # | Section | Anchor | Purpose |
|---|---|---|---|
| 1 | Header / sticky index | — | Navigation, theme toggle |
| 2 | Hero + key numbers | `#top` | Hook, main CTA, four verified facts |
| 3 | Why now | `#why-now` | Windows 10 end of support, momentum |
| 4 | What changed in 2026 | `#whats-new` | Six big shifts, each explained |
| 5 | Release calendar | `#calendar` | Interactive 2026 timeline |
| 6 | Featured distros | `#distros` | Six detailed profiles |
| 7 | More distros worth knowing | `#more-distros` | Eight shorter profiles |
| 8 | Comparison table | `#compare` | Side-by-side facts |
| 9 | Distro finder | `#finder` | Three switches → recommendation |
| 10 | Desktops explained | `#desktops` | GNOME, KDE, COSMIC, Cinnamon, Hyprland… |
| 11 | How distros update | `#release-models` | LTS, rolling, atomic, declarative |
| 12 | Apps and software | `#apps` | How to install apps + alternatives table |
| 13 | Gaming on Linux | `#gaming` | Proton, Steam Deck numbers, anti-cheat, SteamOS |
| 14 | Hardware check | `#hardware` | Requirements, old PCs, NVIDIA, ARM |
| 15 | Switching guide | `#switch` | Eight steps from backup to first week |
| 16 | Glossary | `#glossary` | 20 terms in plain language |
| 17 | FAQ | `#faq` | 12 questions |
| 18 | Get help + sources + footer | `#help` | Communities, sources, legal |

---

## 0. Head / SEO

- `<title>`: Distro Desk: a guide to Linux in 2026
- Meta description: What changed in Linux in 2026, how Ubuntu 26.04, Omarchy 4, Fedora 44, COSMIC and others compare, and how to switch safely. Independent and sourced.
- Open Graph image: hero keycaps on the soft surface, 1200×630.
- Structured data: `FAQPage` JSON-LD for §17.

---

## 1. Header

Wordmark · What's new · Distros · Compare · Find yours · Apps · Gaming · Switch · FAQ
On mobile: a menu button, and the section index becomes a horizontal scrolling strip.
Theme switch (light/dark) drawn as a real toggle.

---

## 2. Hero (`#top`)

**Eyebrow:** Linux in 2026 · Updated September 2026

**Headline (h1):** Linux had a big year. Find the version that fits how you work.

**Subhead:** Ubuntu went Wayland-only, Omarchy rebuilt its desktop, Valve started selling a Linux PC, and Rust moved into the kernel. This guide explains what changed, compares the main distros, and walks you through switching.

**Buttons:** Find your distro → `#finder` · Compare distros → `#compare`

**Visual:** a row of large keycaps with monograms (Ub, Om, Fe, Po, Mi, De). Pressing one sinks it and jumps to that profile.

**Key numbers strip** (four flat readouts in inset wells, each with a source footnote):
- **7.0**: Linux kernel version, released April 12, 2026 *[R§1]*
- **2031**: Ubuntu 26.04 LTS standard support ends *[R§2]*
- **30,006**: Steam games rated Verified or Playable on Steam Deck (Aug 2026) *[R§11, secondary: recheck]*
- **3.90%**: Linux share of Steam users, August 2026 (record 5.33% in March) *[R§11]*

---

## 3. Why now (`#why-now`)

**Heading:** Why so many people are trying Linux

**Body:**
Microsoft ended support for Windows 10 on **October 14, 2025**. Windows 11 needs TPM 2.0, Secure Boot and a recent CPU, so many working PCs can't upgrade. Linux gives those machines security updates for years, at no cost.

People are acting on it. Zorin OS 18, which launched the same day Windows 10 support ended, passed **2 million downloads in under three months**, and Zorin says over three quarters came from Windows users. Steam's own survey put Linux at a **record 5.33% of players in March 2026**.

The software is ready too: Steam runs most Windows games through Proton, Flathub hosts thousands of desktop apps, and the major distros are now Wayland-first with modern security built in.

**Side note panel ("Be careful with market-share headlines"):** Web-traffic trackers reported Linux desktop share anywhere from 3% to 9% in 2026, partly because a lot of traffic is logged as "unknown". The Steam survey is steadier, but it only counts gamers.

---

## 4. What changed in 2026 (`#whats-new`)

**Heading:** Six changes that matter this year

Each item: short title + 2–3 sentence explanation + "Where you'll see it" tags.

1. **Wayland is the default.**
   Wayland replaces the 40-year-old X11 system for drawing windows. It's smoother, handles mixed-DPI monitors better, and stops apps spying on each other's windows. Ubuntu 26.04 removed the GNOME X11 session. KDE plans to go Wayland-only with Plasma 6.8, and Linux Mint is bringing Wayland to Cinnamon. Old X11 apps still run through XWayland.
   *Where: Ubuntu 26.04, Fedora 44, KDE Plasma 6.7, elementary OS 8.1*

2. **Rust moved into the core.**
   Rust prevents whole classes of memory bugs that cause security holes. Rust support in Linux 7.0 is no longer experimental. Ubuntu 26.04 replaced `sudo` and the basic command-line tools with Rust versions (`sudo-rs`, Rust coreutils), and System76 wrote the entire COSMIC desktop in Rust.
   *Where: Linux 7.0, Ubuntu 26.04, Pop!_OS/COSMIC*

3. **Security is on by default.**
   Ubuntu 26.04 can encrypt your disk with the key protected by the computer's TPM chip, so you get encryption without typing an extra password at boot. Fedora is working to make at least 99% of its packages reproducible: anyone can rebuild them and confirm the result matches.
   *Where: Ubuntu 26.04, Fedora 44*

4. **Image-based systems grew up.**
   "Atomic" distros update the whole system in one step. If an update breaks something, you reboot into the previous version. NixOS goes further: your whole system is described in one config file you can copy to another machine.
   *Where: Fedora Atomic, Bazzite, SteamOS, NixOS 26.05*

5. **Gaming went mainstream.**
   Valve released the Steam Machine (a Linux PC) on June 29, 2026, and made SteamOS installable on any desktop with an AMD graphics card. Fedora 44 added NTSYNC for faster Windows-game compatibility. The main remaining blocker is anti-cheat in some multiplayer games (see §13).
   *Where: SteamOS 3.8, Bazzite, CachyOS, Fedora 44*

6. **AI agents arrived on the desktop.**
   Omarchy 4 asks you to pick a default coding agent (Claude Code, Codex, Gemini and others) during setup. Ubuntu 26.04 ships NVIDIA CUDA, AMD ROCm and Intel oneAPI in its archive, making Linux easier to set up for local AI work.
   *Where: Omarchy 4, Ubuntu 26.04, openSUSE*

---

## 5. Release calendar (`#calendar`)

**Heading:** The 2026 release calendar

Slider/dial with stops. Without JS it shows as a plain list.

| Date | Release | One line |
|---|---|---|
| Oct 1, 2025 | openSUSE Leap 16.0 | Enterprise base, new Agama installer |
| Oct 14, 2025 | Zorin OS 18 | Launched the day Windows 10 support ended |
| Dec 11, 2025 | Pop!_OS 24.04 LTS | COSMIC becomes the default desktop |
| Mar 18, 2026 | GNOME 50 "Tokyo" | VRR and fractional scaling on by default, parental controls |
| Apr 12, 2026 | Linux 7.0 | Rust no longer experimental; self-healing XFS |
| Apr 23, 2026 | Ubuntu 26.04 LTS | Wayland-only GNOME, TPM encryption, support until 2031 |
| Apr 28, 2026 | Fedora 44 | GNOME 50, DNF5, GCC 16, NTSYNC |
| May 2026 | NixOS 26.05 "Yarara" | 20,442 new packages |
| Jun 2026 | KDE Plasma 6.7 | Per-screen virtual desktops, HDR + ICC together |
| Jun 2026 | SteamOS 3.8 | Official support for any AMD-GPU desktop |
| Jun 29, 2026 | Steam Machine | Valve's Linux gaming PC goes on sale |
| Jul 1, 2026 | COSMIC 1.2 | *(recheck date)* |
| Aug 14, 2026 | Omarchy 4 "Quattro" | New Quickshell desktop, 24-color themes |
| Sep 12, 2026 | Debian 13.7 | Latest point release of stable "trixie" |
| Dec 2026 (planned) | Linux Mint 23 | Ubuntu 26.04 base, Wayland for Cinnamon, new installer |
| 2027 (planned) | Debian 14 "forky" | Next Debian stable |

---

## 6. Featured distros (`#distros`)

**Heading:** Six distros worth a close look

**Card layout:** raised card. It has a header (monogram keycap, name, version, one-liner), a facts row (Base · Desktop · Updates · Support), **Good for** / **Think twice if**, **What's new**, and an **Official site →** button. On desktop, a "More details" panel opens in place.

### Ubuntu 26.04 LTS "Resolute Raccoon"
*The dependable default, supported until 2031.*
- **Base:** Debian · **Desktop:** GNOME 50 · **Updates:** fixed release, LTS · **Support:** 5 years standard (to April 2031)
- **Good for:** first-time users, work laptops, developers who want the most documentation, servers.
- **Think twice if:** you have less than 6 GB RAM (try Xubuntu or Lubuntu), or you dislike Snap packages.
- **What's new:** Wayland-only GNOME session · Linux 7.0 · TPM-backed full-disk encryption · `sudo-rs` and Rust coreutils · APT 3 · new default apps (Ptyxis terminal, Resources monitor, Showtime video player) · CUDA, ROCm and oneAPI in the archive · Firefox 150, LibreOffice 25.8.
- **Requirements:** 2 GHz dual-core, 6 GB RAM, 25 GB disk.
→ ubuntu.com/download

### Omarchy 4 "Quattro"
*A finished keyboard-driven desktop for developers, by DHH.*
- **Base:** Arch Linux · **Desktop:** Hyprland + Quickshell · **Updates:** rolling · **Support:** community / 37signals
- **Good for:** developers and terminal users who want a good-looking tiling setup without weeks of configuration.
- **Think twice if:** you're new to Linux, prefer using the mouse, or need a fixed-release system.
- **What's new:** the whole desktop shell rebuilt in Quickshell (one menu on Super + Space) · shipped as pacman packages · a 24-color theme system that styles Neovim, VS Code and btop to match · choose a default coding agent · new apps (Omawrite, Omacut, Omacalc) · dual boot and factory reset · ISO under 6 GB, installs about 30% faster.
→ omarchy.org

### Fedora 44
*The latest stable software, close to upstream.*
- **Base:** independent (Red Hat–sponsored) · **Desktop:** GNOME 50 (Workstation), KDE Plasma edition · **Updates:** fixed release about every 6 months · **Support:** about 13 months per release
- **Good for:** developers; anyone who wants new GNOME and KDE versions soon after release.
- **Think twice if:** you want to install once and not upgrade for years.
- **What's new:** GNOME 50 · Plasma Login Manager for KDE · DNF5 · GCC 16, LLVM 22 · NTSYNC for gaming · better ARM support · work towards reproducible builds.
→ fedoraproject.org

### Pop!_OS 24.04 with COSMIC
*A tiling-friendly desktop written in Rust.*
- **Base:** Ubuntu 24.04 · **Desktop:** COSMIC · **Updates:** fixed release, LTS base · **Support:** follows the Ubuntu 24.04 LTS base
- **Good for:** people who want window tiling without config files; NVIDIA users (dedicated NVIDIA ISO); creators.
- **Think twice if:** you rely on GNOME extensions (COSMIC is a different desktop).
- **What's new:** COSMIC is the default since Dec 2025 · tile with the mouse or keyboard · per-display workspaces · automatic HiDPI scaling.
→ system76.com/pop

### Linux Mint
*The gentlest move from Windows.*
- **Base:** Ubuntu LTS · **Desktop:** Cinnamon (also MATE, Xfce) · **Updates:** fixed release · **Support:** follows Ubuntu LTS
- **Good for:** people leaving Windows, older computers, family PCs.
- **Think twice if:** you want the newest desktop features right away.
- **What's coming:** Mint 23 planned for **December 2026** on Ubuntu 26.04 and Linux 7.0, with full Wayland support for Cinnamon and a new installer. Mint is moving to a longer development cycle.
→ linuxmint.com

### Debian 13 "trixie"
*The stable foundation many distros are built on.*
- **Base:** independent · **Desktop:** your choice at install (GNOME, KDE, Xfce and more) · **Updates:** fixed release about every 2 years · **Support:** full until Aug 2028, LTS until Jun 2030
- **Good for:** servers, and people who value predictability over the newest versions.
- **Think twice if:** you need very new drivers for brand-new hardware.
- **What's new:** point release 13.7 (Sep 2026) · Debian 14 "forky" planned for 2027.
→ debian.org

---

## 7. More distros worth knowing (`#more-distros`)

**Heading:** More distros, by what you need

Smaller flat cards in groups.

**Coming from Windows or macOS**
- **Zorin OS 18:** Windows-like layouts, OneDrive integration, a web-app tool and better Windows-app compatibility. Passed 2 million downloads in under 3 months. → zorin.com/os
- **elementary OS 8.1:** a calm, macOS-like desktop. Wayland by default, first ARM64 release, and can be installed entirely with a screen reader. → elementary.io

**Gaming**
- **Bazzite:** Fedora Atomic base with Steam, Lutris, Heroic, MangoHud and GPU drivers preinstalled. Console-like mode for TVs and handhelds, and easy rollback. → bazzite.gg
- **CachyOS:** Arch-based, with optimized kernels and packages for maximum performance. → cachyos.org
- **SteamOS 3.8:** Valve's own OS. Official on Steam Deck, Steam Machine, and now any desktop with an AMD GPU. → store.steampowered.com/steamos

**Power users and professionals**
- **Arch Linux:** rolling release, build it your way, with the famous Arch Wiki. → archlinux.org
- **openSUSE Leap 16 / Tumbleweed:** Leap is built from SUSE's enterprise sources, with yearly updates until 2031. Tumbleweed is a tested rolling release. → get.opensuse.org
- **NixOS 26.05:** your whole system is defined in one config file, so it's reproducible and easy to roll back. → nixos.org

---

## 8. Comparison table (`#compare`)

**Heading:** Side by side

Flat table. Horizontal scroll inside its container on mobile, with the first column pinned. Filter chips: All · Beginner-friendly · Developers · Gaming · Servers.

| Distro | Version (Sep 2026) | Base | Default desktop | Update model | Package tools | Support | Best for |
|---|---|---|---|---|---|---|---|
| Ubuntu | 26.04 LTS | Debian | GNOME 50 | Fixed, LTS | apt, Snap | To Apr 2031 | Everyone, servers |
| Omarchy | 4.0.x | Arch | Hyprland | Rolling | pacman, AUR | Rolling | Developers, keyboard users |
| Fedora | 44 | Independent | GNOME 50 / KDE | Fixed, ~6 months | dnf5, Flatpak | ~13 months | Developers, new software |
| Pop!_OS | 24.04 | Ubuntu | COSMIC | Fixed | apt, Flatpak | Ubuntu 24.04 base | Tiling, NVIDIA |
| Linux Mint | 22.x (23 in Dec) | Ubuntu | Cinnamon | Fixed | apt, Flatpak | Ubuntu LTS base | Windows switchers |
| Debian | 13.7 | Independent | Choice | Fixed, ~2 years | apt | To Jun 2030 (LTS) | Servers, stability |
| Zorin OS | 18 | Ubuntu | Zorin (GNOME-based) | Fixed | apt, Flatpak, Snap | Multi-year | Windows switchers |
| elementary OS | 8.1 | Ubuntu | Pantheon | Fixed | apt, Flatpak | Ubuntu LTS base | macOS switchers |
| Bazzite | rolling images | Fedora Atomic | KDE or GNOME | Atomic | Flatpak, rpm-ostree | Rolling | Gaming, handhelds |
| CachyOS | rolling | Arch | KDE (choice) | Rolling | pacman | Rolling | Gaming, performance |
| SteamOS | 3.8 | Arch | Steam + KDE | Atomic | Flatpak | Valve | Gaming on AMD |
| openSUSE Leap | 16.0 | SUSE Enterprise | KDE / GNOME | Fixed, yearly | zypper, Flatpak | To 2031 (series) | Workstations, enterprise |
| NixOS | 26.05 | Independent | Choice | Declarative | nix | To Dec 31, 2026 | Reproducible setups |

*(Check the Support column for Fedora, Pop!_OS, Zorin and elementary against the official lifecycle pages before launch.)*

---

## 9. Distro finder (`#finder`)

**Heading:** Find yours with three switches

**Intro:** Answer three questions. There's no wrong answer, and you can try another distro later.

1. **How much do you want to tinker?** · Not at all / A little / I enjoy it
2. **What will you mostly do?** · Everyday use / Coding / Gaming / Servers
3. **How do you like to work?** · Mouse and windows / Keyboard and tiling

**Result card:** suggestion + why (one sentence) + Official site + "Also try: …" + "Read the profile ↓".

| Answers | Suggestion | Also try |
|---|---|---|
| No tinkering + everyday + mouse | Linux Mint | Zorin OS |
| A little + everyday + mouse | Ubuntu | elementary OS |
| Coding + keyboard | Omarchy | Pop!_OS |
| Coding + mouse | Fedora | Ubuntu |
| Gaming + no/little tinkering | Bazzite | SteamOS (AMD) |
| Gaming + enjoys tinkering | CachyOS | Bazzite |
| Servers | Debian | Ubuntu Server |
| Mouse + wants tiling | Pop!_OS | Fedora KDE |
| Enjoys tinkering + everyday | Arch Linux | openSUSE Tumbleweed |
| Enjoys tinkering + wants reproducibility | NixOS | Fedora Atomic |

---

## 10. Desktops explained (`#desktops`)

**Heading:** The desktop is what you actually see

**Intro:** A distro and a desktop environment are different things. The desktop is the interface (panels, windows, settings), and most distros offer several. If you don't like the look of a distro, you may only need a different desktop.

Each tile shows a small schematic of the layout (built in CSS, not screenshots) plus a short text.

- **GNOME 50:** clean and focused, driven by an activities overview. VRR and fractional scaling on by default, new parental controls. *Default in Ubuntu and Fedora.*
- **KDE Plasma 6.7:** very customizable, with a familiar taskbar layout. New in 6.7: separate virtual desktops per monitor, and HDR together with color profiles. Wayland-only from 6.8. *Default in Fedora KDE, Bazzite, CachyOS, SteamOS desktop mode.*
- **COSMIC:** System76's Rust desktop. Traditional layout with built-in tiling. *Default in Pop!_OS.*
- **Cinnamon:** a traditional Windows-like layout, easy for switchers. Wayland support in progress. *Default in Linux Mint.*
- **Hyprland:** a tiling window manager: windows arrange themselves automatically and you drive everything from the keyboard. *Default in Omarchy.*
- **Pantheon:** simple and calm, with a dock. *Default in elementary OS.*
- **Xfce / LXQt:** lightweight, for older hardware. *Xubuntu, Lubuntu, Mint Xfce.*

---

## 11. How distros update (`#release-models`)

**Heading:** Four ways a distro updates, and why it matters

Four raised tiles, each with an icon and a "Pick this if…" line.

- **Fixed release / LTS:** big updates arrive on a schedule; in between you get only security and bug fixes. *Pick this if you want stability.* Ubuntu LTS, Debian, Mint, Leap.
- **Rolling release:** there are no versions; you always get the newest software. *Pick this if you want the latest and don't mind occasional fixes.* Arch, Omarchy, CachyOS, Tumbleweed.
- **Atomic (image-based):** the system updates as a whole image, and a bad update can be undone at boot. *Pick this if you want "it just works" and easy recovery.* Bazzite, Fedora Atomic, SteamOS.
- **Declarative:** you describe the system in a file and the OS builds it. *Pick this if you want to rebuild the same setup on any machine.* NixOS.

---

## 12. Apps and software (`#apps`)

**Heading:** Your apps on Linux

**Part A: how you install apps**
1. **The app store:** GNOME Software, KDE Discover, Mint's Software Manager. Point and click, like a phone.
2. **Flatpak / Flathub:** one app store that works on every distro, with sandboxed apps. Thousands of apps, and over 3 billion downloads by 2025.
3. **The package manager:** `apt`, `dnf`, `pacman`, `zypper` for command-line users.
4. **Snap** (Ubuntu) and **AppImage** (one file you download and run).

**Part B: common apps and alternatives** (flat table)

| You use | On Linux |
|---|---|
| Chrome, Firefox, Edge, Brave | Native versions available |
| Microsoft Office | LibreOffice 25.8 (in Ubuntu 26.04), OnlyOffice; Microsoft 365 in the browser |
| Photoshop | GIMP 3.2, Krita (painting), Photopea (browser) |
| Lightroom | darktable, RawTherapee |
| Premiere / Final Cut | Kdenlive, DaVinci Resolve (has a Linux version) |
| Illustrator | Inkscape |
| VS Code, JetBrains IDEs | Native versions available |
| Spotify, Discord, Slack, Zoom, Steam | Native or Flatpak versions available |
| Adobe Creative Cloud, some anti-cheat games | Not available. Check before you switch |

*(Recheck each app's current Linux availability before launch.)*

---

## 13. Gaming on Linux (`#gaming`)

**Heading:** Gaming on Linux, honestly

**Body:** Steam's **Proton** runs most Windows games on Linux with no setup. By August 2026, **30,006 games** were rated Verified or Playable on Steam Deck. Valve now sells the **Steam Machine** and supports **SteamOS on any desktop with an AMD GPU**.

**What works well:** single-player and most Steam games; Epic and GOG games through Heroic; emulators; controllers.
**What doesn't:** some big multiplayer games whose **anti-cheat** isn't enabled for Linux, such as Battlefield 6, Call of Duty and EA Sports FC 26. Easy Anti-Cheat and BattlEye support Linux, but each game's developer has to switch it on.

**Before you switch:** look up your games on **ProtonDB** and the **GamingOnLinux anti-cheat list**.

**Best distros for gaming:** Bazzite (easiest), CachyOS (fastest), SteamOS (AMD, console-like), Fedora 44 (NTSYNC).

**Stat strip:** 3.90% Linux share on Steam (Aug 2026) · 5.33% record (Mar 2026) · ~21% of Linux Steam users are on SteamOS.

---

## 14. Hardware check (`#hardware`)

**Heading:** Will it run on my computer?

- **Modern PC or laptop (2018+, 8 GB RAM or more):** any distro on this page.
- **Ubuntu 26.04 needs:** 2 GHz dual-core CPU, **6 GB RAM**, 25 GB disk.
- **Older PC (2–4 GB RAM):** Xubuntu or Lubuntu (2 GB RAM or more), Linux Mint Xfce.
- **Very old CPU (before ~2008):** openSUSE Leap 16 and others now need x86-64-v2.
- **NVIDIA graphics:** choose a distro with easy NVIDIA drivers: Pop!_OS (NVIDIA ISO), Ubuntu, Bazzite, CachyOS.
- **ARM (e.g. Snapdragon laptops, Raspberry Pi):** Fedora and elementary OS 8.1 have ARM64 builds. Laptop support varies, so check first.
- **Test first:** boot from a USB stick (§15) and check Wi-Fi, sound, display, sleep and the touchpad before installing.

---

## 15. Switching guide (`#switch`)

**Heading:** Switch in eight steps

Numbered steps with a progress rail (a slider-style inset track that fills as you scroll).

1. **Back up everything.** Copy your files to an external drive or the cloud. Export browser bookmarks and passwords.
2. **Check your apps and games** against §12 and ProtonDB.
3. **Pick a distro** with the finder (§9). When unsure, choose Linux Mint or Ubuntu.
4. **Download it from the official site** and check the checksum shown on the download page.
5. **Make a USB stick** with Fedora Media Writer, balenaEtcher or Ventoy (8 GB or larger).
6. **Try it live.** Boot from the USB without installing and check Wi-Fi, sound, display, touchpad and sleep.
7. **Install.** Choose "erase disk" for a clean start, or install next to Windows (dual boot). Turn on disk encryption if it's offered.
8. **First-week checklist:** run updates, install drivers if prompted, enable Flathub, install your apps, set up backups (Déjà Dup, Timeshift or the system's own tool).

**Alternative:** try it in a virtual machine first (GNOME Boxes, VirtualBox, VMware).

---

## 16. Glossary (`#glossary`)

**Heading:** Linux words, in plain language

Searchable list (filter as you type). Without JS it's a definition list.

- **Distro:** a complete Linux-based operating system: the kernel plus desktop, apps and tools.
- **Kernel:** the core that talks to your hardware. Linux 7.0 is the current major version.
- **Desktop environment (DE):** the interface you see and click: GNOME, KDE Plasma, COSMIC…
- **Window manager / compositor:** the part that draws and arranges windows. Hyprland is one.
- **Tiling:** windows arrange themselves side by side automatically instead of overlapping.
- **Wayland:** the modern system for drawing windows on screen, replacing X11.
- **X11 / XWayland:** the old display system, and the layer that runs old X11 apps on Wayland.
- **LTS:** long-term support; years of security updates for one version.
- **Rolling release:** always-updating software with no version numbers.
- **Atomic / immutable:** the system updates as a whole image and can be rolled back.
- **Package manager:** the tool that installs and updates software (apt, dnf, pacman, zypper).
- **Flatpak / Flathub:** a universal app format and its main app store.
- **Snap:** Canonical's universal app format, used in Ubuntu.
- **AUR:** the Arch User Repository; community-made packages for Arch-based distros.
- **ISO:** the installer image file you download.
- **Live USB:** a USB stick that runs Linux without installing it.
- **Dual boot:** two operating systems on one computer; you choose one at startup.
- **Proton:** Valve's tool for running Windows games on Linux.
- **TPM:** a security chip in your computer that can protect disk-encryption keys.
- **Terminal:** a text window for typing commands. Optional on most beginner distros.

---

## 17. FAQ (`#faq`)

Accordion (raised when closed, inset when open).

1. **Is Linux free?** Yes, every distro on this page is free to download and use. Some companies sell paid support (e.g. Ubuntu Pro, SUSE).
2. **Which distro is best for beginners?** Linux Mint or Ubuntu 26.04 LTS. Zorin OS if you want Windows-like layouts, elementary OS if you're coming from a Mac.
3. **Can I keep Windows?** Yes, with dual boot. Back up first.
4. **Do I need to use the terminal?** Not on Mint, Ubuntu, Zorin, Fedora or Pop!_OS. You can do everything with apps and settings. Omarchy and Arch expect you to use it.
5. **Will my printer, Wi-Fi and webcam work?** Usually yes. Test in a live session before installing.
6. **Can I run Microsoft Office or Adobe apps?** Office works in the browser (Microsoft 365). Adobe Creative Cloud doesn't run on Linux; see the alternatives in §12.
7. **Will my games work?** Most Steam games do. Check ProtonDB and the anti-cheat list for multiplayer games.
8. **Is Linux secure?** It has a strong track record, fast security updates, and features such as TPM-backed disk encryption and sandboxed Flatpak apps. Still keep your system updated.
9. **What does "Wayland-only" mean for me?** Nothing for most people. Old apps still run through XWayland. A few older screen-recording and remote tools may need newer versions.
10. **What's the difference between Ubuntu and Linux Mint?** Mint is built on Ubuntu LTS but has a more Windows-like desktop (Cinnamon) and doesn't use Snap by default.
11. **Is Omarchy for beginners?** Not really. It's keyboard-driven and built on Arch. Great for developers who like the terminal.
12. **Is this site affiliated with any of these projects?** No. It's independent. Always download from the official sites.

---

## 18. Get help, sources, footer (`#help`)

**Get help (heading):** You won't be on your own
- Ask Ubuntu (askubuntu.com) · Ubuntu Discourse
- Fedora Discussion (discussion.fedoraproject.org)
- Linux Mint Forums (forums.linuxmint.com)
- Arch Wiki (wiki.archlinux.org), useful for every distro
- Omarchy Manual (learn.omacom.io)
- r/linux4noobs for beginner questions

**Final CTA:** Pick a distro and try it from a USB stick this weekend. → Find your distro

**Sources:** an expandable list of every source from the research file, grouped by topic. Each on-page number links to its source.

**Footer:**
- "Distro Desk is an independent guide. It is not affiliated with Canonical, the Fedora Project, Red Hat, System76, 37signals, Linux Mint, Debian, SUSE, Valve, Zorin, elementary or the NixOS Foundation."
- "Linux® is the registered trademark of Linus Torvalds in the U.S. and other countries. Other names are trademarks of their respective owners."
- "Last updated: September 2026 · Report a correction" (mailto or GitHub issue link).

---

## Open items before building
- [ ] Final site name and domain
- [ ] Logos: text monograms by default; each project's trademark policy decides whether we can use its logo
- [ ] Screenshots: our own from VMs (preferred), or official press kits. Don't hotlink.
- [ ] Recheck every *Secondary* fact and all items marked *(recheck)*
- [ ] Update the Linux Mint card when Mint 23 ships (December 2026)
- [ ] Decide on a corrections contact (email or GitHub issues)
