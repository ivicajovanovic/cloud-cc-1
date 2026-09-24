# Research: modern Linux distros (collected September 2026)

This is the fact base for the landing page. All copy in `content/landing.md` must trace back to a line here.

**Confidence levels**
- **Confirmed**: from the project's own release notes or documentation, or consistent across several independent outlets.
- **Secondary**: from a single news or blog source. Recheck before publishing or leave it out of the copy.
- **Planned**: announced but not released yet. Always write it as "planned" or "expected".

Some official sites (omarchy.org, canonical.com, fedoramagazine.org, phoronix.com, wikipedia.org) were blocked from this research environment. Facts from them were taken from search results and other outlets that quote them. Before launch, open each official link in §9 in a browser and check the numbers.

---

## 1. Release timeline for 2026

| Date | Event | Confidence |
|---|---|---|
| 2025-12-11 | Pop!_OS 24.04 LTS released with the COSMIC desktop as default | Confirmed |
| 2026-03-03 | Pop!_OS 24.04 upgrade opened to existing users | Secondary (not used on the page) |
| 2026-04-12 | Linux kernel 7.0 released | Confirmed |
| 2026-04-23 | Ubuntu 26.04 LTS "Resolute Raccoon" released | Confirmed |
| 2026-04-28 | Fedora Linux 44 released (delayed from April 14) | Confirmed |
| 2026-07-01 | COSMIC desktop 1.2.0 released | Confirmed |
| 2026-07-22 | COSMIC Epoch 1.4 released (latest stable at time of writing) | Confirmed (Phoronix, LinuxCompatible) |
| 2026-08 | Ubuntu 26.04.1 LTS point release | Confirmed |
| 2026-08-14 | Omarchy 4.0 "Quattro" released | Confirmed (GitHub release) |
| 2026-09-12 | Debian 13.7 point release (Debian 13 "trixie") | Confirmed |
| 2026-12 (planned) | Linux Mint 23, based on Ubuntu 26.04 | Planned |
| 2027 (planned) | Debian 14 "forky" | Planned |

---

## 2. Ubuntu 26.04 LTS "Resolute Raccoon"

- Released **April 23, 2026**. Long-term support release: **5 years of standard support, until April 2031**.
- **Linux kernel 7.0**. It was originally planned as 6.20, and the version changed when the upstream kernel was renumbered.
- **GNOME 50**, **Wayland only**: the GNOME-on-X11 session is removed, and XWayland still runs old X11 apps.
- GNOME 50 brings: better fractional scaling, autostart app management in Settings, hardware-accelerated remote desktop (Vulkan/VAAPI), better VRR, Orca screen-reader improvements with a Reduced Motion option, and parental controls with screen-time limits.
- **Memory-safe core tools:** `sudo-rs` is the default `sudo`, and **Rust coreutils** replace the GNU versions.
- **TPM-backed full-disk encryption.**
- **Dracut** replaces initramfs-tools. systemd 259. cgroup v1 removed.
- APT 3 with a new dependency solver. Netplan 1.2.
- Apps: Firefox 150, LibreOffice 25.8, Thunderbird 140, GIMP 3.2. New defaults: **Ptyxis** terminal, **Resources** system monitor, **Showtime** video player.
- AI/ML: NVIDIA CUDA toolkit in the archive, AMD ROCm 7.1, Intel oneAPI/DPC++.
- Secondary: "post-quantum cryptography defaults". Only one outlet mentions it, so don't use it in copy without checking.

**Positioning for the page:** the safe, well-supported default. Best for newcomers, work laptops and servers.

---

## 3. Omarchy 4.0 "Quattro"

- Created by **David Heinemeier Hansson (DHH)**, co-founder of 37signals/Basecamp and creator of Ruby on Rails.
- Built on **Arch Linux** with the **Hyprland** tiling Wayland compositor. Keyboard-driven and opinionated. Self-described as "beautiful, fun & agentic Linux".
- **4.0.0 released August 14, 2026.** Patch releases followed: 4.0.1 (security fixes from the new Omarchy Security team), 4.0.3, and **4.0.4 (September 2026), which makes Omarchy's own tuned kernel (`linux-omarchy`) the default**. Confirmed (GitHub release, Linuxiac). The next major release is being developed as "Quattro RS" (Secondary).
- **The whole desktop shell was rewritten in Quickshell.** Bar, launcher, menus, notifications, on-screen displays, control panels, lock screen and polkit agent now run as one long-running process with a plugin architecture. It replaces Waybar, Walker, Mako, SwayOSD, hyprlock, hypridle, swaybg and polkit-gnome.
- Omarchy is now shipped as **pacman packages** instead of a git checkout, so updates and user changes are safer.
- Hyprland config moved to **Lua** (Hyprland 0.56 compatible).
- One menu on **Super + Space** that includes the launcher. Notification history, a clipboard manager with image previews, an emoji picker, and control panels for audio, Bluetooth, network, display and power.
- **Theming:** a visual theme switcher with live previews. The palette grew from 8 to **24 colors**, so matching Neovim, VS Code and btop themes are generated automatically. New themes: Solitude, Last Horizon, Lupine.
- **New built-in apps:** Omawrite (Markdown editor), Omacut (video trimmer), Omacalc (calculator). Foot is the terminal.
- **Coding agents:** you choose a default agent (Claude Code, Codex, Gemini and others). Herdr is a Rust terminal multiplexer that shows each pane's agent state (idle, working, blocked, done). The Herdr detail is Secondary.
- **Install:** the ISO is over 1 GB smaller (**now under 6 GB**), installs are **about 30% faster** ("sub-minute installs possible"), plus **dual-boot support** and a **factory reset**.
- Hardware tuning: speaker profiles for 2026 Dell XPS 14/16, external monitor brightness over DDC/CI, and better clamshell mode.

**Positioning:** for developers and keyboard-first people who want a finished, good-looking tiling setup without spending weeks on dotfiles.

---

## 4. Fedora Linux 44

- Released **April 28, 2026**.
- Workstation ships **GNOME 50**. The KDE edition gets a unified setup flow and the new **Plasma Login Manager**.
- **DNF5** package manager. **GCC 16**, **LLVM 22**. Ruby 4.0, Go 1.26, PHP 8.5, Django 6.
- Gaming: **NTSYNC** support for better Wine and Steam performance.
- Better ARM/aarch64 support. Work towards **reproducible builds** (goal: ≥ 99% of packages).
- Atomic (image-based) variants exist, such as Silverblue and Kinoite. Bazzite is built on Fedora Atomic.

**Positioning:** the latest stable software with a strong upstream focus. Popular with developers.

---

## 5. Pop!_OS 24.04 + COSMIC

- System76's **COSMIC** desktop is written from scratch **in Rust** (with the Iced toolkit).
- Pop!_OS 24.04 LTS with COSMIC as the default desktop: **December 11, 2025**. COSMIC 1.2.0: July 1, 2026 (Secondary).
- Features: automatic window tiling that works with mouse or keyboard, flexible workspaces (horizontal or vertical, per display, pinnable), and multi-monitor support with automatic HiDPI scaling.

**Positioning:** a modern, tiling-friendly desktop that still feels familiar. Good for creators and people with NVIDIA hardware (System76 ships an ISO with NVIDIA drivers).

---

## 6. Linux Mint (22.x now, 23 planned)

- **Mint 23 is planned for December 2026**, based on Ubuntu 26.04 LTS with kernel 7.0.
- Mint is moving to a **longer development cycle**, starting with Mint 23.
- Planned: **full Wayland support for Cinnamon** and a **new installer** based on the LMDE installer, replacing Ubiquity.

**Positioning:** the easiest move from Windows. Traditional desktop, conservative choices.

---

## 7. Debian 13 "trixie"

- The current stable release. Latest point release **13.7 (September 12, 2026)**.
- Support: full support **until August 9, 2028**, then LTS **until June 30, 2030**.
- Debian 14 "forky" is in testing, with release planned for 2027.

**Positioning:** a stable base that many other distros build on. For servers and people who value predictability over the newest versions.

---

## 8. Gaming distros: CachyOS and Bazzite

- **CachyOS:** Arch-based and tuned for performance (optimized kernels and packages). It shipped KDE Plasma 6.6 early in 2026.
- **Bazzite:** built on **Fedora Atomic** (image-based, easy to roll back). Steam, Lutris, Heroic, MangoHud, GameMode and Proton tools come preinstalled, along with AMD and NVIDIA drivers. It has a console-like handheld/TV mode.
- Secondary, **don't use in copy without checking:** "CachyOS is the #1 gaming distro by Linux Steam user share, 21.1% (Q1–Q2 2026, ProtonDB data)". Linux share of the Steam survey was ~2.2% in early 2026 (the survey changes monthly, so check the current figure).

---

## 9. Big trends (good material for the "What changed" section)

1. **Wayland is the default.** Ubuntu's GNOME session is Wayland-only, Mint's Cinnamon is moving to Wayland, and Fedora is pushing Wayland across its desktops (including Budgie).
2. **Rust is part of the core.** Rust in the kernel is no longer experimental (Linux 7.0). Ubuntu ships sudo-rs and Rust coreutils. COSMIC is written entirely in Rust.
3. **Image-based ("atomic") systems.** Fedora Atomic, Bazzite: updates apply as a whole and you can roll back.
4. **Linux gaming.** Proton/Steam, NTSYNC, and gaming-focused distros (Bazzite, CachyOS).
5. **Agents on the desktop.** Omarchy 4 treats AI coding agents as part of the default setup.
6. **Security by default.** TPM-backed disk encryption (Ubuntu), reproducible builds (Fedora), memory-safe tools.

Linux 7.0 highlights: Rust no longer experimental, self-healing XFS (health monitoring), a standard API for reporting filesystem errors, scheduler time-slice extension (RSEQ), and support for Intel Nova Lake and AMD Zen 6.

---

## 10. Sources

Official sources: open these in a browser before launch to check the facts above.
- Ubuntu 26.04 release notes: https://documentation.ubuntu.com/release-notes/26.04/
- Ubuntu 26.04 summary for LTS users: https://documentation.ubuntu.com/release-notes/26.04/summary-for-lts-users/
- Canonical announcement: https://canonical.com/blog/canonical-releases-ubuntu-26-04-lts-resolute-raccoon
- Omarchy: https://omarchy.org/
- Omarchy v4.0.0 release notes: https://github.com/omacom/omarchy/releases/tag/v4.0.0
- Fedora 44 announcement: https://fedoramagazine.org/announcing-fedora-linux-44/
- Debian trixie: https://www.debian.org/releases/trixie/
- System76 COSMIC updates: https://blog.system76.com/post/cosmic-epoch-1-updates/
- Linux 7.0 (Kernel Newbies): https://kernelnewbies.org/Linux_7.0

News and secondary sources:
- It's FOSS, Ubuntu 26.04 features: https://itsfoss.com/ubuntu-26-04-release-features/
- OMG! Ubuntu, 26.04.1: https://www.omgubuntu.co.uk/2026/08/ubuntu-26041-lts-point-release-download
- Phoronix, Omarchy 4.0: https://www.phoronix.com/news/Omarchy-4.0-Released
- Linuxiac, Omarchy 4.0: https://linuxiac.com/arch-based-omarchy-4-0-quattro-is-here-with-its-biggest-desktop-overhaul-yet/
- Code To Cloud, Omarchy 4: https://codetocloud.io/blog/omarchy-4-quattro-whats-new/
- OSTechNix, Fedora 44 date: https://ostechnix.com/fedora-44-release-date-confirmed/
- The Register, Fedora 44: https://www.theregister.com/software/2026/04/29/fedora-44-is-out-countless-versions-of-it/5224584
- 9to5Linux, Mint development cycle: https://9to5linux.com/linux-mint-will-adopt-a-longer-development-cycle-starting-with-linux-mint-23
- OMG! Ubuntu, Mint 23 timing: https://www.omgubuntu.co.uk/2026/04/linux-mint-next-release-christmas-2026
- OSTechNix, Linux 7.0: https://ostechnix.com/linux-kernel-7-0-released/
- 9to5Linux, Linux 7.0: https://9to5linux.com/linux-kernel-7-0-officially-released-this-is-whats-new
- XDA, gaming distros: https://www.xda-developers.com/if-youre-choosing-a-linux-distro-for-gaming-try-these-two-first/
- Tech2Geek, Bazzite vs CachyOS vs Nobara: https://www.tech2geek.net/linux-gaming-in-2026-bazzite-vs-cachyos-vs-nobara-which-distro-should-you-choose/

---

## 11. Additional research (round 2)

### More distros
- **Zorin OS 18**: released **October 14, 2025**, the day Windows 10 support ended. Aimed at people coming from Windows: several Windows-like layouts, OneDrive integration, built-in web-app (PWA) tool, improved Windows-app compatibility (Wine). Passed **2 million downloads in under 3 months**, with over three quarters from Windows users (Zorin's own figures). Confirmed.
- **elementary OS 8.1**: a polished, macOS-like desktop (Pantheon). Wayland is the default "Secure Session". First stable **ARM64** ISO. Blind users can install and set it up entirely with a screen reader. Over 1,100 issues fixed. Confirmed.
- **openSUSE Leap 16.0**: released **October 1, 2025**. Built from SUSE Linux Enterprise 16 sources, binary-identical at the core. New **Agama** installer replaces YaST's installer. Needs an **x86-64-v2** CPU (roughly 2008 or newer). Yearly minor releases planned until 16.6 in 2031. Confirmed.
- **openSUSE Tumbleweed**: rolling release. In 2026 snapshots shipped Plasma 6.6.x and GNOME 50. Confirmed.
- **NixOS 26.05 "Yarara"**: released in May 2026. **Declarative**: the whole system is described in one config file, upgrades are atomic, and you can roll back. **20,442 new packages**, systemd-based initrd by default, **2,842 contributors**. Supported until **2026-12-31**. Confirmed (nixos.org blog).
- **Arch Linux**: rolling release, build-it-yourself. Often first to ship new desktops (e.g. it was first with KDE Plasma 6.5). Omarchy, CachyOS, EndeavourOS and SteamOS are built on Arch.
- **SteamOS**: Valve's Arch-based gaming OS. With **SteamOS 3.8 (June 2026)** Valve officially supports any desktop PC **with an AMD GPU**. **Steam Machine** (Valve hardware running SteamOS) released **June 29, 2026**: US$1,049 (512 GB) / US$1,349 (2 TB). Secondary for the prices.

### Desktop environments
- **GNOME 50 "Tokyo"**: released **March 18, 2026**. VRR and fractional scaling on by default, parental controls with screen-time limits and bedtime, faster thumbnails in Files, hardware-accelerated remote desktop, GTK 4.22. Default in Ubuntu 26.04 and Fedora 44 Workstation. Confirmed (release.gnome.org).
- **KDE Plasma 6.7**: released **June 2026**. **Per-screen virtual desktops** (a long-requested feature), simultaneous HDR and ICC color profiles, many Wayland improvements before Plasma 6.8 becomes **Wayland-only**, the new "Union" theming engine, the "Air" theme back. Confirmed.
- **COSMIC** (System76, Rust), **Cinnamon** (Mint, Wayland in progress), **Hyprland** (tiling Wayland compositor used by Omarchy), **Pantheon** (elementary), **Xfce/LXQt** (lightweight: Xubuntu, Lubuntu).

### Hardware requirements
- **Ubuntu 26.04 Desktop:** 2 GHz dual-core CPU, **6 GB RAM**, 25 GB storage. It's the first minimum-RAM increase since 2019. For older PCs Canonical points to flavors such as **Xubuntu/Lubuntu (2 GB RAM or more)**. Server starts at 1.5 GB RAM and 4 GB storage. Confirmed.
- **openSUSE Leap 16:** x86-64-v2 CPU.
- **Omarchy 4:** ISO under 6 GB. Needs a 64-bit x86 PC and is tuned for recent laptops (e.g. Dell XPS 2026).

### Apps and software
- **Flathub** (the main Flatpak app store): about **4.3 billion total downloads** and **3,542 apps** in 2026. Secondary (single source). Earlier confirmed milestone: 3 billion downloads, and over 1 million active users (Flathub's own blog).
- Ways to install apps: the distro's software store; native packages (apt, dnf, pacman, zypper); **Flatpak** (works on every distro, sandboxed); **Snap** (Ubuntu); **AppImage** (one file, no install).

### Gaming
- **Steam Hardware Survey, August 2026:** Linux **3.90%** (record **5.33% in March 2026**). SteamOS is about 21% of Linux Steam users. Confirmed (GamingOnLinux, Phoronix).
- **Steam Deck ratings (SteamDB, Aug 31, 2026):** about 8,939 Verified and 21,067 Playable, **30,006 Verified or Playable** in total. **Confirmed** (GamingOnLinux, PC Gamer, KitGuru, PC Guide: "nearly 9,000 officially Verified"). Some articles swap the two sub-numbers; only use the total on the page.
- **Anti-cheat is the main blocker:** Easy Anti-Cheat and BattlEye support Proton, but only if the game's developer turns it on. Several big multiplayer titles (e.g. Battlefield 6, Call of Duty, EA Sports FC 26) don't run. Check the GamingOnLinux anti-cheat list or ProtonDB before switching.

### Why people are switching
- **Windows 10 support ended October 14, 2025.** Many PCs can't upgrade to Windows 11 because of its TPM 2.0, Secure Boot and CPU requirements. Linux is a supported way to keep using them. Confirmed.
- Desktop market share: StatCounter figures swing a lot in 2026 (from ~3% to ~9% worldwide in different months), and a large share of pageviews is "Unknown". **Don't quote a StatCounter share on the page**; the Steam survey is more stable to cite.

### Sources (round 2)
- openSUSE Leap 16 announcement: https://news.opensuse.org/2025/10/01/next-chapter-opens-with-leap-release/
- Get Leap 16.0: https://get.opensuse.org/leap/16.0/
- NixOS 26.05 announcement: https://nixos.org/blog/announcements/2026/nixos-2605/
- Zorin OS 18: https://blog.zorin.com/2025/10/14/zorin-os-18-has-arrived/
- TechRepublic, Zorin 2M downloads: https://www.techrepublic.com/article/news-zorin-os-2m-downloads-windows-10-support-ends/
- elementary OS 8.1: https://blog.elementary.io/os-8-1-available-now/
- GNOME 50 release notes: https://release.gnome.org/50/
- OMG! Ubuntu, GNOME 50: https://www.omgubuntu.co.uk/2026/03/gnome-50-released
- OMG! Ubuntu, Plasma 6.7: https://www.omgubuntu.co.uk/2026/06/kde-plasma-6-7-released
- KDE Plasma 6.7.1: https://kde.org/announcements/plasma/6/6.7.1/
- OMG! Ubuntu, Ubuntu 26.04 requirements: https://www.omgubuntu.co.uk/2026/04/ubuntu-2604-system-requriments
- Hackster, 6 GB RAM: https://www.hackster.io/news/canonical-bumps-ubuntu-26-04-lts-s-system-requirements-now-asks-for-6gb-of-ram-1ccc21e4a370
- TheSixthAxis, SteamOS 3.8 on AMD PCs: https://www.thesixthaxis.com/2026/06/22/you-can-now-install-steamos-3-8-on-your-standard-gaming-pc-with-amd-gpu/
- PCGamesN, Steam Machine: https://www.pcgamesn.com/steam-machine/launch
- GamingOnLinux, Steam survey Aug 2026: https://www.gamingonlinux.com/2026/09/steam-linux-user-share-dips-below-4-percent-for-august-2026/
- GamingOnLinux, anti-cheat list: https://www.gamingonlinux.com/anticheat/
- Proton compatibility stats: https://commandlinux.com/statistics/proton-game-compatibility-on-linux/
- Flathub, 1M active users: https://docs.flathub.org/blog/over-one-million-active-users-and-growing
- OSTechNix, Flathub 3B downloads: https://ostechnix.com/flathub-3-billion-downloads/
- Linux market share caveats: https://pbxscience.com/desktop-linux-reaches-8-88-worldwide-in-august-2026-but-the-surge-comes-with-caveats/

---

## 12. General-knowledge facts used in "What is Linux?" (add sources before launch)
- Android phones run on the Linux kernel. **Confirmed** (source.android.com)
- The Steam Deck runs SteamOS, which is based on Arch Linux (see §11: SteamOS). Confirmed.
- Linus Torvalds announced Linux on August 25, 1991; it's named after him. **Confirmed** (XDA, Linux.com)
- Linux is open source (GPL license since 1992): anyone can read, change and share the code. **Confirmed**

---

## 13. Fact check, September 24, 2026 (online verification)

| Claim | Result | Sources |
|---|---|---|
| 30,006 Steam games Verified or Playable on Steam Deck (Aug 2026) | **Confirmed** (total). Sub-split corrected: ~8,939 Verified, ~21,067 Playable | GamingOnLinux, PC Gamer, PC Guide, KitGuru |
| COSMIC 1.2 on July 1, 2026 | **Confirmed**, but no longer the latest: **COSMIC 1.4 on July 22, 2026** | Linux Adictos; Phoronix; LinuxCompatible |
| Pop!_OS 24.04 LTS + COSMIC on December 11, 2025 | **Confirmed** | OMG! Ubuntu, 9to5Linux, System76 blog |
| Ubuntu 26.04 LTS on April 23, 2026, 5 years of free security updates | **Confirmed** | Ubuntu announce list, Canonical |
| Linux Mint 23 planned for December 2026 | **Confirmed as planned**; betas expected around Sep–Oct | GamingOnLinux, 9to5Linux, Mint forums |
| Linux Mint disables Snap by default | **Confirmed** | Linux Mint User Guide |
| Fedora: new release about every 6 months, each supported about 13 months | **Confirmed** | Fedora Release Life Cycle |
| Android runs on the Linux kernel | **Confirmed** | source.android.com (Kernel overview) |
| Linus Torvalds announced Linux on August 25, 1991; named after him; GPL (open source) since 1992 | **Confirmed** | XDA, Linux.com, History of Linux |
| Battlefield 6 and Call of Duty don't run on Linux/Steam Deck | **Confirmed**. EA says it plans Linux/Proton support for its Javelin anti-cheat, with no date | ProtonDB, Tom's Hardware, GamingOnLinux, EA forums |
| Steam Machine went on sale around June 29, 2026 from US$1,049 | **Confirmed** (purchase invitations from the week of June 29) | Dexerto, SlashGear |
| Omarchy latest version | **4.0.4** (September 2026) | GitHub releases, Linuxiac |

**Not used on the page (left unverified on purpose):** CachyOS share of Linux Steam users, Flathub 4.3 billion downloads, Herdr details, "post-quantum defaults" in Ubuntu 26.04, StatCounter market share.

**Sources (fact check):**
- https://www.gamingonlinux.com/2026/08/steam-deck-steamos-hit-over-30-000-verified-playable-games/
- https://www.pcgamer.com/hardware/handheld-gaming-pcs/30-000-games-are-either-steam-deck-verified-or-at-least-playable-on-valves-handheld/
- https://www.pcguide.com/news/steam-deck-hits-30000-compatible-games-milestone-with-nearly-9000-officially-verified-by-valve/
- https://en.linuxadictos.com/cosmic-1-2-arrives-with-key-improvements-for-system76's-rust-desktop.html
- https://www.phoronix.com/news/COSMIC-Epoch-1.4
- https://www.linuxcompatible.org/story/system76-releases-cosmic-epoch-140-with-stability-fixes-and-compositor-updates/
- https://www.omgubuntu.co.uk/2025/12/pop_os-24-04-lts-stable-release
- https://9to5linux.com/system76-launches-first-stable-release-of-cosmic-desktop-and-pop_os-24-04-lts
- https://lists.ubuntu.com/archives/ubuntu-announce/2026-April/000323.html
- https://www.gamingonlinux.com/2026/04/linux-mint-confirm-longer-release-cycles-the-next-release-is-planned-for-christmas-2026/
- https://linuxmint-user-guide.readthedocs.io/en/latest/snap.html
- https://docs.fedoraproject.org/en-US/releases/lifecycle/ (Fedora Release Life Cycle)
- https://source.android.com/docs/core/architecture/kernel
- https://www.xda-developers.com/on-this-day-in-1991-linus-torvalds-announced-linux/
- https://www.linux.com/news/linus-torvalds-reflects-25-years-linux/
- https://www.protondb.com/app/2807960
- https://www.tomshardware.com/video-games/battlefield-6s-javelin-anti-cheat-secure-boot-requirement-could-kill-its-steam-deck-support
- https://www.gamingonlinux.com/2025/08/battlefield-6-will-be-a-unplayable-on-linux-systems-due-to-the-anti-cheat/
- https://www.dexerto.com/gaming/steam-machine-finally-launches-as-valve-reveals-1049-starting-price-3378373/
- https://github.com/omacom/omarchy/releases/tag/v4.0.4
- https://linuxiac.com/omarchy-4-0-4-makes-its-custom-linux-kernel-the-default/
