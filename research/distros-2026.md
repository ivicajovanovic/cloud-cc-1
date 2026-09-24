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
| 2026-03-03 | Pop!_OS 24.04 upgrade opened to existing users | Secondary |
| 2026-04-12 | Linux kernel 7.0 released | Confirmed |
| 2026-04-23 | Ubuntu 26.04 LTS "Resolute Raccoon" released | Confirmed |
| 2026-04-28 | Fedora Linux 44 released (delayed from April 14) | Confirmed |
| 2026-07-01 | COSMIC desktop 1.2.0 released | Secondary |
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
- **4.0.0 released August 14, 2026.** Patch releases 4.0.1 (security fixes, from the new Omarchy Security team) and 4.0.3 followed.
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
