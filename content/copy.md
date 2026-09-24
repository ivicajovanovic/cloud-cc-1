# Distro L. Desk: final copy (v2, beginner-first)

This is the **approved, ready-to-publish text** for every part of the site. The build uses this file word for word.
- Layout, interactions and design notes: `content/landing.md`
- Facts and sources: `research/distros-2026.md`. Numbers marked **[S]** come from a single source and must be rechecked before launch.
- Text in `[brackets]` is a placeholder to fill in before launch.

**About the name:** *Distro L. Desk* is a nod to Philip K. Dick, who wrote about machines, reality and the people caught between them. The reference appears in three places only: the footer colophon, the 404 page and the "About the name" note. Everywhere else the copy stays practical.

**Audience:** most visitors are beginners, young people and non-technical users coming from Windows or macOS. Tech-savvy readers are welcome, but they're not who the page is written for.

**The pattern for every section**
1. **Plain-language opening (always visible):** an eyebrow, a friendly h2, and an "In short" paragraph of 2–4 sentences. No jargon, no version numbers unless they help (like "until 2031"), no brand names that a beginner wouldn't know.
2. **The details:** the technical content, in a "Show the details" panel. It's collapsed by default unless the section notes say otherwise (practical content such as the apps table and the switching steps stays visible).

**Style rules for any future edits**
- Openings: plain English at about the reading level of a 14-year-old. Short sentences, everyday words, one idea per sentence.
- Say "version" in openings; say "distro" only after it's been explained (in "What is Linux?"), and use both freely after that.
- Write in the second person ("you"), in short sentences.
- Give specific facts with versions and dates. Avoid adjectives like "powerful", "seamless" or "cutting-edge".
- Explain every technical term the first time it appears, or link it to the glossary.
- Never promise that something "just works". Say what works and what to check.
- British or American spelling: **American**, used consistently.

---

## 0. Site-wide text

**Site name:** Distro L. Desk
**Tagline:** A friendly, independent guide to Linux.

**`<title>` (home):** Distro L. Desk: a friendly, independent guide to Linux in 2026
**Meta description:** New to Linux? A friendly, independent guide to choosing a version, checking your apps and games, and switching safely from Windows or macOS. Updated September 2026.
**Open Graph title:** Give your computer a fresh start with Linux.
**Open Graph description:** Pick a Linux version in three questions, check your apps and games, and switch step by step. Free, independent and sourced.
**OG image alt:** The words "Give your computer a fresh start with Linux" on a soft blue-to-peach gradient, above a Linux desktop screenshot.

**Skip link:** Skip to main content
**Theme toggle (aria-label):** Switch between light and dark theme
**Theme toggle (visible labels):** Light · Dark
**Back to top (aria-label):** Back to top
**External link hint (screen readers only):** (opens the official site)
**Source-link pattern:** a small superscript number next to a fact. Screen-reader text: "Source [n]"

**"Show the details" control (used in every section)**
- Closed: Show the details
- Open: Hide the details
- Accessible pattern: a native `<details>`/`<summary>` element. The summary text reads "Show the details: [section heading]" for screen readers.

---

## 1. Header and section index

**Wordmark:** Distro L. Desk

**Main navigation**
| Label | Anchor |
|---|---|
| What is Linux? | `#what-is-linux` |
| Help me choose | `#finder` |
| Versions | `#distros` |
| Apps | `#apps` |
| Gaming | `#gaming` |
| How to switch | `#switch` |
| FAQ | `#faq` |

**Mobile menu button:** Menu / Close menu
**Section index heading (screen readers only):** On this page

**Section index short labels (in page order):** Start · Basics · Why now · Choose · Versions · Apps · Gaming · Your PC · Switch · New in 2026 · Timeline · More versions · Compare · Desktops · Updates · Glossary · FAQ · Help

---

## 2. Hero (`#top`)

The hero speaks to people who have never used Linux: no version numbers, jargon or distro abbreviations. Every section below follows the same pattern: a plain-language opening first, then "Show the details" for anyone who wants the technical side.

**Eyebrow:** A friendly guide to Linux · Updated September 2026

**Headline (h1):** Give your computer a fresh start with Linux.

**Subhead:**
Linux is a free alternative to Windows and macOS. It runs on most computers, including many that can't upgrade to Windows 11, and it gets regular security updates. This guide helps you choose a version, try it without risk and switch one step at a time.

**Primary button:** Help me choose → `#finder`
**Secondary button:** How to switch → `#switch`

**Choice panel**
- **Heading:** What matters to you?
- **Choice pills** (icon + label; the selected pill turns ink with white text and updates the suggestion line):

| Key label | Icon (Lucide-style) | Suggestion shown |
|---|---|---|
| Feels like Windows | Screen with a taskbar | Linux Mint |
| Feels like a Mac | Screen with a top bar and dock | elementary OS |
| Just works | Check mark in a circle | Ubuntu |
| Older computer | Laptop | Linux Mint Xfce |
| Gaming | Game controller | Bazzite |
| Coding | Code brackets | Fedora |

- **Suggestion line:** Suggestion: [Distro] · See why (links to that distro's profile)
- **Default state (nothing pressed):** Press a key to see a suggestion.
- **Panel accessible name:** What matters to you? Choose one to see a suggested Linux version.

**Key numbers strip** (heading, screen readers only: "Linux in four facts")
| Figure | Label | Source |
|---|---|---|
| Free | Every Linux version in this guide costs nothing to download and use | Official project sites |
| 2031 | Ubuntu 26.04 gets free security updates until 2031 | Ubuntu release notes |
| 30,000+ | Steam games rated Verified or Playable on the Linux-based Steam Deck | SteamDB via GamingOnLinux and PC Gamer |
| Oct 2025 | Windows 10 support ended. Linux gives those PCs a supported option | Microsoft, via TechRepublic |

---

## 3. What is Linux? (`#what-is-linux`)

**Plain-language opening (always visible)**
- **Eyebrow:** The basics
- **Heading (h2):** What is Linux, in plain words?
- **In short:** Linux is the software that runs a computer, like Windows or macOS. It's free, anyone can use it, and it already runs Android phones and the Steam Deck. You don't install "Linux" on its own. You pick a ready-made version of it, called a **distro**, which comes with a desktop, apps and settings, a bit like choosing a new phone.

**Layout:** two split rows (see `design.md` §16).

**Row 1** (text left, illustration right)
- Uses the eyebrow, heading and "In short" above, plus the "Show the details" button.
- **Illustration:** a dashed ring of six distro pills (Ubuntu, Linux Mint, Fedora, Pop!_OS, Debian, Omarchy) around a white card reading **"Linux kernel"** (desktop adds a second line: "the shared core").
- **Illustration alt text:** Six Linux versions (Ubuntu, Linux Mint, Fedora, Pop!_OS, Debian and Omarchy) arranged in a ring around the Linux kernel they all share.

**Row 2** (illustration left, text right)
- **Eyebrow:** Free, and safe to try
- **Heading (h3, styled large):** Free to use, and safe to try first.
- **Body:** Install it on as many computers as you like, at no cost. Better still, you can run it from a USB stick first and see how it feels, without touching anything on your computer.
- **Button (primary):** How to switch → `#switch`
- **Illustration:** two tilted screenshot cards (Linux Mint and Ubuntu) and a pill reading **"Running from USB · nothing installed"**.
- **Illustration alt text:** Two Linux desktops shown as screenshots, with a note that they are running from a USB stick without being installed.

**The details** (collapsed by default)
- **Distro** is short for *distribution*: a complete package made of the Linux **kernel** (the core that talks to your hardware), a **desktop** (what you see and click), apps and tools.
- Different teams build different distros. Canonical makes Ubuntu, the Fedora Project makes Fedora, a small community team makes Linux Mint, and so on. They share code, which is why most apps work on all of them.
- Linux is named after its creator, Linus Torvalds, who announced it on August 25, 1991.
- Linux is **open source** (under the GPL license since 1992): anyone can read the code, fix it and share improvements. That's why it's free.
- Links to glossary: Distro · Kernel · Desktop environment

**Sources:** see `research/distros-2026.md` §12–13 (verified September 24, 2026).

---

## 4. Why now (`#why-now`)

**Plain-language opening (always visible)**
- **Eyebrow:** Why now
- **Heading (h2):** Why so many people are trying Linux right now
- **In short:** Windows 10 stopped getting security updates in October 2025, and many computers can't upgrade to Windows 11. Linux gives those computers free updates for years. Games, apps and setup have also become much easier, so switching is less of a leap than it used to be.

**The details** (collapsed by default)

Microsoft ended support for Windows 10 on October 14, 2025. Windows 11 requires a TPM 2.0 chip, Secure Boot and a recent processor, so millions of working computers can't be upgraded. Without updates, those machines become less safe every month. Linux gives them years of security updates, at no cost.

People noticed. Zorin OS 18, released the same day Windows 10 support ended, passed 2 million downloads in under three months, and Zorin reports that more than three quarters of those came from Windows users. On Steam, Linux reached a record 5.33% of players in March 2026 and has stayed between 3% and 4% since.

The software is ready for them too. Steam runs most Windows games through a compatibility layer called Proton. Flathub, the cross-distro app store, offers thousands of desktop apps. The biggest distros now ship modern graphics, disk encryption backed by your computer's security chip, and memory-safe core tools by default.

**Callout title:** A note on market-share headlines
**Callout body:**
You may see claims that Linux now runs on 5%, 9% or even 10% of desktops. These numbers come from web-traffic trackers that changed a lot through 2026, and a large share of their traffic is logged as "unknown" operating system. We don't quote them. The Steam survey is steadier, but it only counts people who play games on Steam.

---

## 5. Distro finder (`#finder`)

**Plain-language opening (always visible)**
- **Eyebrow:** Three questions
- **Heading (h2):** Not sure which one? Answer three questions.
- **In short:** There's no single "best" Linux. The right one depends on what you do and how you like to work. Flip three switches and we'll suggest a good place to start. Nothing you choose is stored or sent anywhere.

**The details** (none: the finder is the content)

**Question 1:** How hands-on do you want to be?
- Not at all: I want it to work out of the box
- A little: I'll change a few settings
- I enjoy it: I like to build my own setup

**Question 2:** What will you mostly use it for?
- Everyday use: web, email, documents, video
- Coding
- Gaming
- Running servers

**Question 3:** How do you like to work?
- With the mouse and overlapping windows
- With the keyboard and tiled windows

**Switch labels (short, shown on the switches) with helper text (shown under the switch for the selected option):**
| Question | Switch label | Helper text |
|---|---|---|
| 1 | Not at all | I want it to work out of the box |
| 1 | A little | I'll change a few settings |
| 1 | I enjoy it | I like to build my own setup |
| 2 | Everyday | Web, email, documents, video |
| 2 | Coding | Writing and running code |
| 2 | Gaming | Steam and other game launchers |
| 2 | Servers | Running services and websites |
| 3 | Mouse | With the mouse and overlapping windows |
| 3 | Keyboard | With the keyboard and tiled windows |

**Result eyebrow:** Your suggestion

**Before answering (result area):** Flip the three switches to see a suggestion.
**Result heading pattern:** Try [Distro]
**Result buttons:** Official site · Read the profile
**"Also try" label:** Also worth a look:
**Reset button:** Start again
**No-JS fallback heading:** Quick guide: which distro for whom

**Result texts**
| Result | Why (one or two sentences) |
|---|---|
| **Linux Mint** | It works the way Windows does, it avoids surprises, and it gets updates for years. The easiest first step. *Also try: Zorin OS* |
| **Ubuntu 26.04 LTS** | The most popular Linux for everyday computers, with free updates until 2031 and an answer online for almost every question. *Also try: elementary OS* |
| **Omarchy 4** | A ready-made coding setup you control with the keyboard, with developer tools and AI coding assistants ready from day one. *Also try: Pop!_OS* |
| **Fedora 44** | Up-to-date tools for coding, tested carefully before release, with a new version twice a year. *Also try: Ubuntu 26.04 LTS* |
| **Bazzite** | Steam, drivers and game launchers come ready to go, and a bad update can be undone when you start the computer. *Also try: SteamOS (AMD graphics only)* |
| **CachyOS** | Built for speed, for players who like to fine-tune their setup. *Also try: Bazzite* |
| **Debian 13** | Rock-solid, changes slowly and gets updates until 2030. Great for servers. *Also try: Ubuntu Server* |
| **Pop!_OS with COSMIC** | Windows arrange themselves neatly side by side, and you can still do everything with the mouse. *Also try: Fedora KDE* |
| **Arch Linux** | You build your system piece by piece and learn how Linux works along the way. Keep the Arch Wiki open. *Also try: openSUSE Tumbleweed* |
| **NixOS 26.05** | Your whole setup lives in one file, so you can rebuild it on any computer or undo any change. *Also try: Fedora Atomic* |

---

## 6. Featured distros (`#distros`)

**Plain-language opening (always visible)**
- **Eyebrow:** Where to start
- **Heading (h2):** Six good places to start
- **In short:** A distro is a ready-to-use version of Linux. These six cover almost everyone. If you're new, start with **Linux Mint** or **Ubuntu**: they're friendly, well supported, and have huge communities that happily answer beginner questions.

**The details** (per card, collapsed by default)

**Card layout:** the plain-language lines are always visible. Everything else (Based on · Desktop · Updates · Support · Good for · Think twice if · What's new · Hardware) sits in the card's details panel.
**Card buttons:** More details / Fewer details · Official site
**Official-site button (aria pattern):** "Visit the official [Distro] website (opens the official site)"

### 6.1 Ubuntu 26.04 LTS "Resolute Raccoon"
**In plain words (always visible):** The most popular Linux for everyday computers. Easy to install, with free updates until 2031.
**You'll like it if (always visible):** you want something mainstream, with an answer online for every question.
**One-liner:** The dependable default, supported until 2031.
**Summary:** Ubuntu is the most widely documented Linux distro. If you search for how to do something on Linux, the answer is usually written for Ubuntu first. Version 26.04 is a long-term support release, which means five years of standard security updates without having to upgrade.
- **Based on:** Debian
- **Desktop:** GNOME 50
- **Updates:** Fixed release, long-term support
- **Support:** Standard support until April 2031
- **Good for:** First-time Linux users, work laptops, developers who want the widest documentation, and servers.
- **Think twice if:** Your computer has less than 6 GB of RAM (try Xubuntu or Lubuntu instead), or you'd rather avoid Snap, Ubuntu's own app format.
- **What's new:** GNOME runs on Wayland only. Linux 7.0 kernel. Full-disk encryption protected by the TPM chip. `sudo` and core command-line tools rewritten in Rust. A faster APT 3 package manager. New default apps: Ptyxis (terminal), Resources (system monitor) and Showtime (video player). NVIDIA CUDA, AMD ROCm and Intel oneAPI available from the official archive. Firefox 150 and LibreOffice 25.8.
- **Hardware:** 2 GHz dual-core processor, 6 GB RAM, 25 GB of storage.

### 6.2 Omarchy 4 "Quattro"
**In plain words (always visible):** A stylish setup for programmers, controlled almost entirely from the keyboard.
**You'll like it if (always visible):** you write code and love keyboard shortcuts. Not meant for first-timers.
**One-liner:** A finished, keyboard-driven desktop for developers.
**Summary:** Omarchy is an opinionated setup created by David Heinemeier Hansson (DHH), co-founder of 37signals and creator of Ruby on Rails. It turns Arch Linux into a polished tiling desktop, where windows arrange themselves and you control everything from the keyboard. Version 4 rebuilt the whole interface.
- **Based on:** Arch Linux
- **Desktop:** Hyprland, with a new Quickshell interface
- **Updates:** Rolling release
- **Support:** Community-supported, maintained by the Omarchy team
- **Good for:** Developers and terminal users who want a good-looking tiling setup without spending weeks on configuration files.
- **Think twice if:** You're new to Linux, you prefer the mouse, or you want a system that changes only on a fixed schedule.
- **What's new:** The bar, launcher, notifications, lock screen and control panels now form a single interface, opened from one menu with Super + Space. Omarchy now installs as regular system packages, which makes updates safer. A theme system with 24 colors restyles Neovim, VS Code and btop to match. You choose a default AI coding agent during setup. New built-in apps for writing, trimming video and calculating. Dual-boot support and a factory reset option. The installer shrank below 6 GB and runs about 30% faster.
- **Hardware:** A 64-bit Intel or AMD computer. Tuned for recent laptops, including the 2026 Dell XPS 14 and 16.

### 6.3 Fedora 44
**In plain words (always visible):** Always-fresh software, tested carefully before it reaches you.
**You'll like it if (always visible):** you want the newest features and don't mind upgrading about once a year.
**One-liner:** The latest stable software, close to the source.
**Summary:** Fedora, sponsored by Red Hat, ships new versions of GNOME, KDE and developer tools soon after they're released, and tests them carefully first. Many features that later reach other distros show up in Fedora first.
- **Based on:** Independent
- **Desktop:** GNOME 50 (Workstation) or KDE Plasma (KDE edition)
- **Updates:** Fixed release, roughly every six months
- **Support:** About 13 months per version
- **Good for:** Developers, and anyone who wants new desktop features without running a rolling release.
- **Think twice if:** You want to install once and not upgrade for several years.
- **What's new:** GNOME 50. A new login screen for the KDE edition. The DNF5 package manager is faster and more reliable. GCC 16 and LLVM 22 compilers. NTSYNC for better Windows-game performance. Better support for ARM computers. Steady progress towards reproducible builds.
- **Hardware:** Most computers from the last ten years. ARM64 builds are available.

### 6.4 Pop!_OS 24.04 with COSMIC
**In plain words (always visible):** A modern desktop that can arrange your windows neatly for you.
**You'll like it if (always visible):** you juggle lots of windows, or you have an NVIDIA graphics card.
**One-liner:** A tiling-friendly desktop written in Rust.
**Summary:** Pop!_OS is made by System76, a company that sells Linux computers. Its new COSMIC desktop looks familiar, with a panel and a dock, but can also tile windows automatically, and it works with the mouse as well as the keyboard.
- **Based on:** Ubuntu 24.04 LTS
- **Desktop:** COSMIC
- **Updates:** Fixed release on a long-term support base
- **Support:** Follows the Ubuntu 24.04 LTS base
- **Good for:** People who want tiling without editing config files, owners of NVIDIA graphics cards, and creative work.
- **Think twice if:** You depend on GNOME extensions, which don't work in COSMIC.
- **What's new:** COSMIC has been the default desktop since December 2025. Tile windows with the mouse or keyboard. Workspaces can be set per monitor and pinned. High-resolution screens are scaled automatically.
- **Hardware:** A 64-bit Intel or AMD computer. A separate download includes NVIDIA drivers.

### 6.5 Linux Mint
**In plain words (always visible):** The easiest move from Windows. The menu, taskbar and settings feel familiar straight away.
**You'll like it if (always visible):** you want your computer to feel familiar and stay calm.
**One-liner:** The gentlest move from Windows.
**Summary:** Linux Mint takes Ubuntu's long-term support base and adds a desktop that feels immediately familiar to Windows users, with a start menu, a taskbar and a system tray. It favors careful, conservative changes, which is exactly what many newcomers want.
- **Based on:** Ubuntu LTS
- **Desktop:** Cinnamon (MATE and Xfce editions also available)
- **Updates:** Fixed release
- **Support:** Follows the Ubuntu LTS base
- **Good for:** People leaving Windows, older computers and shared family PCs.
- **Think twice if:** You want the newest desktop features as soon as they appear.
- **What's coming:** Linux Mint 23 is planned for December 2026. It is expected to be built on Ubuntu 26.04 with Linux 7.0, and to bring full Wayland support to Cinnamon and a new installer. Mint is also moving to a longer development cycle.
- **Hardware:** Modest. The Xfce edition runs well on older machines.

### 6.6 Debian 13 "trixie"
**In plain words (always visible):** Rock-solid and slow to change. Many other versions are built on it.
**You'll like it if (always visible):** you want a system that stays the same for years, or you're running a server.
**One-liner:** The stable foundation many distros build on.
**Summary:** Debian is one of the oldest community-run distros, and Ubuntu, Mint, Pop!_OS and many others are built on it. It changes slowly and deliberately, which makes it a favorite for servers and for anyone who wants a system that stays the same.
- **Based on:** Independent
- **Desktop:** Your choice during installation, including GNOME, KDE Plasma and Xfce
- **Updates:** Fixed release, roughly every two years
- **Support:** Full support until August 2028, long-term support until June 2030
- **Good for:** Servers, and people who value predictability over the newest versions.
- **Think twice if:** You have brand-new hardware that needs very recent drivers.
- **What's new:** Point release 13.7 arrived on September 12, 2026. Debian 14 "forky" is planned for 2027.
- **Hardware:** Runs on almost anything, including older 64-bit PCs and ARM boards.

---

## 7. Apps and software (`#apps`)

**Plain-language opening (always visible)**
- **Eyebrow:** Your apps
- **Heading (h2):** Will my apps work?
- **In short:** Mostly, yes. Your browser, Spotify, Discord, Zoom, Steam and VS Code all run on Linux. For Microsoft Office you can use the web version or a free alternative. Adobe's apps are the big exception, but there are good free replacements. Installing apps works like on your phone: open the app store, search, press Install.

**The details** (the apps table is always visible; "How you install apps" is collapsed)

### Apps you use today (visible, shown first)
**Subheading (h3):** Common apps and what to use on Linux
**Table caption:** Popular Windows and macOS apps and their Linux versions or alternatives.
**Column headers:** You use · On Linux

| You use | On Linux |
|---|---|
| Chrome, Firefox, Edge, Brave | The same browsers, native versions |
| Microsoft Office | LibreOffice (included in most distros) or OnlyOffice; Microsoft 365 works in the browser |
| Adobe Photoshop | GIMP 3.2, or Krita for digital painting; Photopea runs in the browser |
| Adobe Lightroom | darktable or RawTherapee |
| Adobe Premiere, Final Cut Pro | Kdenlive, or DaVinci Resolve, which has an official Linux version |
| Adobe Illustrator | Inkscape |
| VS Code, JetBrains IDEs | The same apps, native versions |
| Spotify, Discord, Slack, Zoom, Steam | The same apps, as native or Flatpak versions |
| Adobe Creative Cloud apps | Not available on Linux; use the alternatives above |

**Note under table:** Check any specialist software you depend on, such as tax, accounting or industry tools, before you switch. Many have web versions.

### How you install apps (inside "Show the details")
**Subheading (h3):** Four ways to install software

1. **The app store.** Every beginner-friendly distro has one: GNOME Software, KDE Discover or Mint's Software Manager. Search, click Install, done.
2. **Flatpak and Flathub.** Flathub is an app store that works on almost every distro. Apps run in a sandbox, separated from the rest of your system, and developers publish updates directly. By 2025 it had passed 3 billion downloads.
3. **The package manager.** Each distro has a command-line tool for installing software: `apt` on Ubuntu, Debian and Mint, `dnf` on Fedora, `pacman` on Arch, `zypper` on openSUSE. You don't need it, but it's there when you want it.
4. **Snap and AppImage.** Snap is Ubuntu's own app format. An AppImage is a single file you download and run, with nothing to install.

---

## 8. Gaming on Linux (`#gaming`)

**Plain-language opening (always visible)**
- **Eyebrow:** Gaming
- **Heading (h2):** Can I game on Linux?
- **In short:** Yes, and better than ever. Most Steam games run with no extra setup. The main exception is some big online games, such as Call of Duty and Battlefield 6, whose anti-cheat software blocks Linux. Check your favorite games before you switch.

**The details** (collapsed by default; the "Before you switch" callout stays visible)

Steam includes Proton, a compatibility layer that runs Windows games on Linux with no setup. As of August 2026, 30,006 games were rated Verified or Playable on the Steam Deck, which runs the same technology. Valve now sells the Steam Machine, a living-room PC running SteamOS, and supports SteamOS on any desktop PC with an AMD graphics card.

**Subheading (h3):** What works well
Most single-player games on Steam. Epic and GOG games through the Heroic launcher. Emulators. Controllers, including Xbox, PlayStation and Steam controllers.

**Subheading (h3):** What doesn't work yet
Some popular online multiplayer games, including Battlefield 6, Call of Duty and EA Sports FC 26, refuse to run because their anti-cheat software doesn't support Linux. Easy Anti-Cheat and BattlEye can work on Linux, but each game's developer has to switch that on, and many haven't. EA says it plans to bring its own anti-cheat to Linux, but hasn't given a date.

**Callout title:** Before you switch
**Callout body:** Look up the games you play most on ProtonDB and on the GamingOnLinux anti-cheat list. If a must-play online game is marked "Broken", keep Windows alongside Linux for now.
**Callout links:** ProtonDB · GamingOnLinux anti-cheat list

**Subheading (h3):** Best distros for gaming
- **Bazzite:** the easiest start, with everything preinstalled
- **CachyOS:** tuned for maximum performance
- **SteamOS:** the console experience, on AMD graphics
- **Fedora 44:** a general-purpose distro with NTSYNC for faster games

**Stat strip (heading, screen readers only: "Linux gaming in numbers")**
| Figure | Label |
|---|---|
| 3.90% | Linux share of Steam players, August 2026 |
| 5.33% | Record high, March 2026 |
| About 21% | Share of Linux Steam players using SteamOS |

---

## 9. Hardware check (`#hardware`)

**Plain-language opening (always visible)**
- **Eyebrow:** Your computer
- **Heading (h2):** Will it run on my computer?
- **In short:** Almost certainly. Linux runs on most computers from the last ten years, and lighter versions can bring an old laptop back to life. The safest way to find out is to try it from a USB stick first, which changes nothing on your computer.

**The details** (the table is collapsed; the "Test before you install" callout stays visible)

| Your computer | What to know |
|---|---|
| **A modern PC or laptop** (from about 2018, 8 GB RAM or more) | Every distro on this page will run well. |
| **Planning to use Ubuntu 26.04** | You need a 2 GHz dual-core processor, 6 GB of RAM and 25 GB of storage. |
| **An older PC** (2 to 4 GB RAM) | Choose a lightweight option: Xubuntu, Lubuntu or Linux Mint Xfce. |
| **A very old processor** (from before about 2008) | Some distros, including openSUSE Leap 16, now require a newer processor feature level (x86-64-v2). Debian and lightweight distros are your best options. |
| **NVIDIA graphics** | Pick a distro that makes NVIDIA drivers easy: Pop!_OS (separate NVIDIA download), Ubuntu, Bazzite or CachyOS. |
| **An ARM computer** (Snapdragon laptops, Raspberry Pi) | Fedora and elementary OS 8.1 offer ARM versions. Support for ARM laptops is still uneven, so check your model first. |

**Callout title:** Test before you install
**Callout body:** Start Linux from a USB stick without installing anything, then check that Wi-Fi, sound, the display, the touchpad and sleep all work. The switching guide below shows how.

---

## 10. Switching guide (`#switch`)

**Plain-language opening (always visible)**
- **Eyebrow:** Step by step
- **Heading (h2):** How to switch, step by step
- **In short:** Plan for an afternoon. Back up your files, put Linux on a USB stick and try it out. Only install it when you're happy, and you can keep Windows alongside it if you like.

**The details** (the eight steps are always visible; the virtual machine callout is collapsed)

**Progress label (aria pattern):** "Step [n] of 8"

1. **Back up everything.**
   Copy your documents, photos and other files to an external drive or cloud storage. Export your browser bookmarks and make sure you can sign in to your password manager.

2. **Check your apps and games.**
   Go through the apps table above and look up your games on ProtonDB. Note anything that has no Linux version.

3. **Choose a distro.**
   Use the distro finder. If you're unsure, pick Linux Mint or Ubuntu 26.04 LTS. Both are safe first choices.

4. **Download it from the official site.**
   Only download from the distro's own website. On the download page you'll find a checksum, a long code you can use to confirm the file wasn't damaged or tampered with.

5. **Put Linux on a USB stick.**
   Use a USB stick of 8 GB or more. Write the downloaded file to it with Fedora Media Writer, balenaEtcher or Ventoy. This erases the USB stick, not your computer.

6. **Try it without installing.**
   Restart your computer and start it from the USB stick. You usually open the boot menu with a key like F12, F2 or Esc at startup. Most distros open a "live" session, so you can check Wi-Fi, sound, the display, the touchpad and sleep. Nothing on your computer changes.

7. **Install.**
   Choose "Erase disk" for a clean start, or "Install alongside" to keep your current system and pick one at startup (dual boot). Turn on disk encryption if the installer offers it.

8. **Your first week.**
   Install all updates. Accept any driver the system suggests. Turn on Flathub (the biggest Linux app store) if your distro doesn't include it. Install your apps. Set up automatic backups with the built-in backup tool, Déjà Dup or Timeshift.

**Callout title:** Prefer to try it in a window first?
**Callout body:** Install a free virtual machine app such as GNOME Boxes, VirtualBox or VMware Workstation, and run any distro inside your current system. It's slower than a real install, but completely risk-free.

---

## 11. What's new in 2026 (`#whats-new`)

**Deep-dive divider (above this section, flat, centered):** That's everything you need to get started. Want to go deeper? The rest of the page is for the curious.

**Plain-language opening (always visible)**
- **Eyebrow:** New this year
- **Heading (h2):** What's new in Linux this year
- **In short:** 2026 brought smoother graphics, stronger security that's on from the start, easier gaming, and systems that can undo a bad update. You don't need to know the technical names to benefit from any of it.

**The details** (per item, collapsed by default)

### Smoother, safer screens
**In plain words (always visible):** Scrolling and video look smoother, and apps can no longer peek at each other's windows.
**Technical name:** Wayland
**Details (collapsed):**
Wayland is the modern system that draws windows on your screen. It replaces X11, which dates back to 1984. With Wayland, scrolling and video are smoother, laptops with high-resolution screens next to ordinary monitors look sharp on both, and apps can't secretly read what's in other apps' windows. Ubuntu 26.04 removed the X11 option from its GNOME desktop entirely. KDE plans to do the same with Plasma 6.8, and Linux Mint is adding Wayland support to Cinnamon. Older apps still run through a compatibility layer called XWayland.
**Where you'll see it:** Ubuntu 26.04 · Fedora 44 · KDE Plasma 6.7 · elementary OS 8.1

### Fewer security holes at the core
**In plain words (always visible):** Important parts of Linux are being rewritten in a newer, safer programming language that rules out whole types of bugs.
**Technical name:** Rust
**Details (collapsed):**
Rust is a programming language that prevents whole categories of memory bugs, which have historically caused many serious security holes. Linux 7.0 made Rust a permanent, non-experimental part of the kernel. Ubuntu 26.04 replaced two tools almost every Linux user touches, `sudo` and the basic command-line utilities, with Rust rewrites. System76 built its entire COSMIC desktop in Rust.
**Where you'll see it:** Linux 7.0 · Ubuntu 26.04 · Pop!_OS with COSMIC

### Your data stays safe if your laptop is stolen
**In plain words (always visible):** Ubuntu can now lock your whole disk using a security chip in your computer, with no extra password at startup.
**Technical name:** TPM-backed encryption and reproducible builds
**Details (collapsed):**
Ubuntu 26.04 can encrypt your whole disk and keep the key in your computer's TPM security chip, so your data is protected if the laptop is stolen, without an extra password at every boot. Fedora is working towards making at least 99% of its packages reproducible, which means anyone can rebuild them from source and confirm nothing was slipped in along the way.
**Where you'll see it:** Ubuntu 26.04 · Fedora 44

### Updates you can undo
**In plain words (always visible):** Some versions now update like a phone. If something breaks, you pick yesterday's version when you start the computer.
**Technical name:** Atomic (image-based) systems
**Details (collapsed):**
An "atomic" distro updates the whole system in one piece, the way a phone does. If an update causes a problem, you pick the previous version at startup and carry on. NixOS goes a step further: your entire setup lives in one configuration file, and you can rebuild the same system on another computer from it.
**Where you'll see it:** Bazzite · Fedora Atomic · SteamOS · NixOS 26.05

### Gaming went mainstream
**In plain words (always visible):** Valve now sells its own Linux gaming PC, and more games run on Linux than ever.
**Technical name:** SteamOS, Steam Machine, NTSYNC
**Details (collapsed):**
Valve released the Steam Machine, a living-room PC running SteamOS, on June 29, 2026. Six days earlier, it made SteamOS officially installable on any desktop PC with an AMD graphics card. Fedora 44 added NTSYNC, a kernel feature that helps Windows games run faster. The main thing still holding Linux gaming back is anti-cheat software in some online games, which we cover honestly in the gaming section.
**Where you'll see it:** SteamOS 3.8 · Bazzite · CachyOS · Fedora 44

### AI helpers on the desktop
**In plain words (always visible):** Some versions now set up AI coding assistants for you, and running AI on your own computer got easier.
**Technical name:** AI coding agents, CUDA, ROCm, oneAPI
**Details (collapsed):**
Omarchy 4 asks you to choose a default AI coding agent, such as Claude Code, Codex or Gemini, as part of its setup, and builds its terminal tools around it. Ubuntu 26.04 now includes NVIDIA's CUDA, AMD's ROCm and Intel's oneAPI in its official software archive, which makes it far simpler to run AI models on your own hardware.
**Where you'll see it:** Omarchy 4 · Ubuntu 26.04 · openSUSE

**Tag label (screen readers only):** Where you'll see it:

---

## 12. Release calendar (`#calendar`)

**Plain-language opening (always visible)**
- **Eyebrow:** Timeline
- **Heading (h2):** The year in releases
- **In short:** A quick timeline of the biggest Linux releases from late 2025 until now. Drag the slider, or use the arrow keys, to move through the year.

**The details** (none: the timeline is the content. Entry texts may use technical names because this is a deep-dive section)

**Slider label (aria):** Release date
**Slider value text (aria pattern):** "[Date]: [Release name]"
**"Planned" badge:** Planned

| Date | Release | Text |
|---|---|---|
| October 1, 2025 | openSUSE Leap 16.0 | Built from SUSE's enterprise sources, with a new installer called Agama and yearly updates planned until 2031. |
| October 14, 2025 | Zorin OS 18 | Released on the day Windows 10 support ended, with layouts that feel familiar to Windows users. |
| December 11, 2025 | Pop!_OS 24.04 LTS | System76's own COSMIC desktop, written in Rust, becomes the default. |
| March 18, 2026 | GNOME 50 "Tokyo" | Variable refresh rate and fractional scaling on by default, plus parental controls with screen-time limits. |
| April 12, 2026 | Linux 7.0 | Rust support is no longer experimental, and the XFS filesystem can now report and help repair its own damage. |
| April 23, 2026 | Ubuntu 26.04 LTS | Wayland-only GNOME, disk encryption through the TPM chip, and standard support until 2031. |
| April 28, 2026 | Fedora 44 | GNOME 50, the faster DNF5 package manager, GCC 16 and better gaming performance through NTSYNC. |
| May 2026 | NixOS 26.05 "Yarara" | 20,442 new packages from 2,842 contributors. |
| June 2026 | KDE Plasma 6.7 | Separate virtual desktops for each monitor, a feature users had requested for years. |
| June 2026 | SteamOS 3.8 | Valve officially supports SteamOS on any desktop PC with an AMD graphics card. |
| June 29, 2026 | Steam Machine | Valve's own Linux gaming PC goes on sale. |
| July 22, 2026 | COSMIC 1.4 | The latest update to System76's Rust desktop, with dozens of stability fixes. |
| August 14, 2026 | Omarchy 4 "Quattro" | A rebuilt desktop shell, a 24-color theme system and an installer under 6 GB. |
| September 12, 2026 | Debian 13.7 | The latest update to Debian's stable release, "trixie". |
| December 2026 | Linux Mint 23 (planned) | Expected on an Ubuntu 26.04 base, with Wayland support for Cinnamon and a new installer. |
| 2027 | Debian 14 "forky" (planned) | The next stable Debian release. |

---

## 13. More distros (`#more-distros`)

**Plain-language opening (always visible)**
- **Eyebrow:** More versions
- **Heading (h2):** More versions, for specific needs
- **In short:** Beyond the big six, there are versions made for gamers, for people coming from a Mac, and for people who love to customize everything. Here are the best-known ones, grouped by who they're for.

**The details** (cards always visible)

**Group filter (aria):** Show distros for

### Group: Coming from Windows or macOS
**Zorin OS 18.** Made for people leaving Windows. It offers several layouts that look like Windows, connects to OneDrive, turns websites into desktop apps, and runs many Windows programs through a compatibility layer. It passed 2 million downloads in under three months.
**elementary OS 8.1.** A calm, carefully designed desktop that will feel familiar to Mac users. It uses Wayland by default, offers its first stable version for ARM computers, and can be installed and set up entirely with a screen reader.

### Group: Gaming
**Bazzite.** The easiest way to turn a PC or handheld into a gaming machine. Steam, Lutris, Heroic, MangoHud and graphics drivers come preinstalled, a console-style mode suits TVs, and a bad update can be undone at startup. Built on Fedora Atomic.
**CachyOS.** An Arch-based distro that compiles its kernel and packages for maximum performance. A favorite among players who like to tune their system.
**SteamOS 3.8.** Valve's own operating system, which powers the Steam Deck and the Steam Machine. It is now officially supported on any desktop PC with an AMD graphics card.

### Group: For people who love to customize
**Arch Linux.** A rolling release you build up yourself, piece by piece. Its wiki is one of the best Linux references ever written and helps users of every distro.
**openSUSE Leap 16 and Tumbleweed.** Leap is built from SUSE's enterprise sources and receives yearly updates until 2031. Tumbleweed is a rolling release that goes through automated testing before every update.
**NixOS 26.05.** You describe your whole system in one configuration file, and NixOS builds it. You can copy that file to another machine and get the same system, or roll back any change.

**Card button:** Official site

---

## 14. Comparison table (`#compare`)

**Plain-language opening (always visible)**
- **Eyebrow:** Side by side
- **Heading (h2):** Compare them side by side
- **In short:** The same facts for fourteen versions in one table: what each is built on, how it looks, how it updates and how long it's supported. Use the filters to show only the ones for beginners, gamers or coders.

**The details** (none: the table is the content (facts as of September 2026))

**Filter chips:** All · For beginners · For coders · For gamers · For servers
**Filter group label (aria):** Filter distros
**No results text:** No distros match this filter. Choose "All" to see the full list.
**Table caption:** Fourteen Linux distros compared by base, desktop, update model, software tools, support and best use, September 2026.

**Column headers:** Distro · Current version · Based on · Default desktop · How it updates · Software tools · Support · Best for

| Distro | Current version | Based on | Default desktop | How it updates | Software tools | Support | Best for | Filters |
|---|---|---|---|---|---|---|---|---|
| Ubuntu | 26.04 LTS | Debian | GNOME 50 | Fixed, long-term support | apt, Snap | Until April 2031 | Most people, servers | Beginner, Developers, Servers |
| Omarchy | 4.0.4 | Arch Linux | Hyprland | Rolling | pacman, AUR | Rolling | Developers, keyboard users | Developers |
| Fedora | 44 | Independent | GNOME 50 or KDE | Fixed, about every 6 months | dnf5, Flatpak | About 13 months | Developers, new software | Developers |
| Pop!_OS | 24.04 | Ubuntu | COSMIC | Fixed | apt, Flatpak | Ubuntu 24.04 base | Tiling, NVIDIA users | Beginner, Developers |
| Linux Mint | 22.x (23 planned) | Ubuntu | Cinnamon | Fixed | apt, Flatpak | Ubuntu LTS base | Windows switchers | Beginner |
| Debian | 13.7 | Independent | Your choice | Fixed, about every 2 years | apt | Until June 2030 | Servers, stability | Servers |
| Zorin OS | 18 | Ubuntu | Zorin (GNOME-based) | Fixed | apt, Flatpak, Snap | Several years | Windows switchers | Beginner |
| elementary OS | 8.1 | Ubuntu | Pantheon | Fixed | apt, Flatpak | Ubuntu LTS base | Mac switchers | Beginner |
| Bazzite | Continuous images | Fedora Atomic | KDE or GNOME | Atomic | Flatpak, rpm-ostree | Continuous | Gaming, handhelds | Beginner, Gaming |
| CachyOS | Rolling | Arch Linux | KDE Plasma (choice) | Rolling | pacman | Rolling | Gaming, performance | Gaming |
| SteamOS | 3.8 | Arch Linux | Steam + KDE Plasma | Atomic | Flatpak | Valve | Gaming on AMD PCs | Gaming |
| Arch Linux | Rolling | Independent | None (you choose) | Rolling | pacman, AUR | Rolling | Tinkerers | Developers |
| openSUSE Leap | 16.0 | SUSE Enterprise | KDE or GNOME | Fixed, yearly | zypper, Flatpak | 16.x series until 2031 | Workstations, business | Developers, Servers |
| NixOS | 26.05 | Independent | Your choice | Declarative | nix | Until December 31, 2026 | Reproducible setups | Developers, Servers |

**Footnote:** Support periods for Fedora, Pop!_OS, Zorin OS and elementary OS follow their own or their base's lifecycle; check the official pages for exact dates. "Rolling" means there are no fixed versions: the system is always up to date.

---

## 15. Desktops explained (`#desktops`)

**Plain-language opening (always visible)**
- **Eyebrow:** How it looks
- **Heading (h2):** How it looks: desktops explained
- **In short:** On Linux, the look of your screen (the menus, the taskbar, the windows) is called the desktop, and you get to choose it. Some look like Windows, some like a Mac, some are completely different. Don't like the look of a version? Often you can switch the desktop and keep everything else.

**The details** (the desktop tiles are always visible; the version details in each tile are collapsed)

**Tile labels:** Feels like · Default in

| Desktop | Description | Feels like | Default in |
|---|---|---|---|
| **GNOME 50** | Clean and focused. You open apps and switch windows from a single overview screen. Version 50 turns on smooth variable refresh rate and sharper scaling by default, and adds parental controls with screen-time limits. | A tablet with a keyboard | Ubuntu, Fedora Workstation |
| **KDE Plasma 6.7** | Highly customizable, with a familiar taskbar at the bottom. Version 6.7 lets each monitor have its own virtual desktops and supports HDR together with color profiles. Wayland-only from version 6.8. | Windows, if you could change everything | Fedora KDE, Bazzite, CachyOS, SteamOS desktop mode |
| **COSMIC** | System76's desktop written in Rust. A traditional layout with a panel and dock, plus built-in automatic tiling you can switch on and off. | A classic desktop that can tile | Pop!_OS |
| **Cinnamon** | A traditional layout with a start menu and taskbar, designed to be easy for people coming from Windows. Wayland support is in progress. | Windows 7 and 10 | Linux Mint |
| **Hyprland** | A tiling compositor: windows arrange themselves side by side and you control everything from the keyboard, with smooth animations. | A cockpit for your keyboard | Omarchy |
| **Pantheon** | Simple, calm and consistent, with a dock at the bottom. | macOS | elementary OS |
| **Xfce and LXQt** | Lightweight and traditional, using very little memory. | A classic desktop that stays quick on old hardware | Xubuntu, Lubuntu, Linux Mint Xfce |

**Schematic alt text pattern:** "Simplified layout of the [Desktop] desktop: [short description of panels and windows]."
- GNOME: Simplified layout of the GNOME desktop: a thin top bar and a full-screen overview of open windows.
- KDE Plasma: Simplified layout of the KDE Plasma desktop: a taskbar along the bottom with a start menu at the left.
- COSMIC: Simplified layout of the COSMIC desktop: a top panel, a dock and three tiled windows.
- Cinnamon: Simplified layout of the Cinnamon desktop: a taskbar along the bottom with a menu and system tray.
- Hyprland: Simplified layout of Hyprland: four tiled windows filling the screen with small gaps and a thin top bar.
- Pantheon: Simplified layout of the Pantheon desktop: a top bar and a centered dock at the bottom.
- Xfce and LXQt: Simplified layout of a lightweight desktop: a single bottom panel and one window.

---

## 16. How distros update (`#release-models`)

**Plain-language opening (always visible)**
- **Eyebrow:** Updates
- **Heading (h2):** How updates work
- **In short:** Some versions update in big steps once or twice a year. Others update a little every day. Some update like a phone and can undo a bad update. If you're new, pick one with big, scheduled updates, like Ubuntu or Linux Mint: it stays calm and predictable.

**The details** (the four tiles are always visible)

**Tile label:** Pick this if · Examples

**Fixed release and long-term support**
Big updates arrive on a schedule, every six months or every few years. Between them you only get security fixes and bug fixes, so nothing changes under your feet.
*Pick this if:* you want a system that stays the same until you decide to upgrade.
*Examples:* Ubuntu LTS, Debian, Linux Mint, openSUSE Leap

**Rolling release**
There are no version numbers. New software arrives as soon as it's ready, in a steady stream of small updates.
*Pick this if:* you want the newest software and don't mind fixing the occasional problem.
*Examples:* Arch Linux, Omarchy, CachyOS, openSUSE Tumbleweed

**Atomic (image-based)**
The system updates as one complete image, like a phone or a games console. If an update goes wrong, you choose the previous image at startup.
*Pick this if:* you want something that's hard to break and easy to recover.
*Examples:* Bazzite, Fedora Atomic, SteamOS

**Declarative**
You write down what your system should contain, and the distro builds exactly that. The same file produces the same system on any computer.
*Pick this if:* you manage several machines or want every change recorded.
*Examples:* NixOS

---

## 17. Glossary (`#glossary`)

**Plain-language opening (always visible)**
- **Eyebrow:** Reference
- **Heading (h2):** Linux words, in plain language
- **In short:** Stuck on a word? Look it up here. Every term is explained in one or two everyday sentences.

**The details** (none: the glossary is the content)

**Search label:** Search the glossary
**Search placeholder:** Type a word, e.g. Wayland
**No results text:** No term matches "[query]". Try a shorter word.
**Result count (aria-live pattern):** "[n] terms shown"

| Term | Definition |
|---|---|
| **Atomic** | A system that updates as one complete image and can go back to the previous version at startup. Also called image-based or immutable. |
| **AUR** | The Arch User Repository: a large collection of community-made install scripts for Arch-based distros such as Omarchy and CachyOS. |
| **Desktop environment** | The interface you see and click: panels, menus, windows and settings. GNOME, KDE Plasma and COSMIC are desktop environments. |
| **Distro** | Short for distribution: a complete operating system built around the Linux kernel, with a desktop, apps and tools. |
| **Dual boot** | Two operating systems on one computer. You choose which one to start each time you turn it on. |
| **Flatpak** | A way of packaging apps so the same app runs on almost any distro, isolated in a sandbox. |
| **Flathub** | The main app store for Flatpak apps. |
| **ISO** | The installer file you download. You write it to a USB stick to start or install a distro. |
| **Kernel** | The core of the operating system, which talks to your hardware. Linux itself is a kernel; the current major version is 7.0. |
| **Live USB** | A USB stick that runs a distro without installing it, so you can try it risk-free. |
| **LTS** | Long-term support: one version that gets security updates for several years. |
| **Package manager** | The tool that installs, updates and removes software, such as apt, dnf, pacman or zypper. |
| **Proton** | Valve's compatibility layer that lets Windows games run on Linux through Steam. |
| **Rolling release** | A distro with no fixed versions, where new software arrives continuously. |
| **Snap** | Canonical's app format, used mainly on Ubuntu. |
| **Terminal** | A window where you type commands. Optional on most beginner-friendly distros. |
| **Tiling** | A way of arranging windows side by side automatically, so they never overlap. |
| **TPM** | A security chip in most modern computers. It can hold the key that unlocks an encrypted disk. |
| **Wayland** | The modern system for drawing windows on screen, which replaces X11. |
| **X11 and XWayland** | X11 is the older display system. XWayland lets older X11 apps run on a Wayland desktop. |

---

## 18. FAQ (`#faq`)

**Plain-language opening (always visible)**
- **Eyebrow:** Questions
- **Heading (h2):** Questions people ask
- **In short:** Short answers to the questions beginners ask most. Tap a question to open the answer.

**The details** (none: each answer is an accordion item)

**Accordion controls (aria):** Expand answer / Collapse answer
**Expand all / Collapse all:** Open all answers · Close all answers

1. **Is Linux really free?**
   Yes. Every distro on this page is free to download, install and use on as many computers as you like. Some companies sell optional paid support for businesses, such as Canonical's Ubuntu Pro and SUSE's enterprise subscriptions.

2. **Which distro is best for a beginner?**
   Linux Mint or Ubuntu 26.04 LTS. Choose Zorin OS if you want a desktop that looks like Windows, or elementary OS if you're coming from a Mac.

3. **Can I keep Windows and try Linux?**
   Yes. You can try Linux from a USB stick without installing it, run it in a virtual machine, or install it next to Windows and choose one at startup. Back up your files before installing anything.

4. **Do I have to use the terminal?**
   Not on Linux Mint, Ubuntu, Zorin OS, Fedora or Pop!_OS. Everyday tasks, including installing apps and updates, work through normal windows and settings. Omarchy and Arch Linux expect you to be comfortable with the terminal.

5. **Will my printer, Wi-Fi and webcam work?**
   Usually, yes. Most hardware works without installing drivers. To be sure, start Linux from a USB stick and test everything before you install.

6. **Can I run Microsoft Office or Adobe apps?**
   Microsoft 365 works in the browser, and LibreOffice opens Word, Excel and PowerPoint files. Adobe Creative Cloud apps don't run on Linux, but GIMP, Krita, Inkscape, darktable, Kdenlive and DaVinci Resolve cover most of the same work.

7. **Will my games work?**
   Most Steam games do, thanks to Proton. Some online multiplayer games with anti-cheat don't. Check your games on ProtonDB and the GamingOnLinux anti-cheat list before switching.

8. **Is Linux secure?**
   Linux has a strong security record, gets fast security updates, and increasingly ships protections by default, such as disk encryption and sandboxed apps. As with any system, install updates and only download software from trusted sources.

9. **What does "Wayland-only" mean for me?**
   For most people, nothing you'll notice, apart from smoother graphics. Older apps still run through XWayland. A few older screen-recording or remote-desktop tools may need a newer version.

10. **What's the difference between Ubuntu and Linux Mint?**
    Linux Mint is built on Ubuntu's long-term support base, but it uses the Cinnamon desktop, which feels more like Windows, and it doesn't use Snap packages by default. Ubuntu uses GNOME and gets new releases first.

11. **Is Omarchy good for beginners?**
    Not really. It's built on Arch Linux and designed to be used from the keyboard. It's excellent for developers who already like the terminal. Beginners will have an easier start with Linux Mint, Ubuntu or Pop!_OS.

12. **Is this site connected to any of these projects?**
    No. Distro L. Desk is independent and isn't sponsored by any distro or company. Always download from the official sites we link to.

---

## 19. Get help, sources and footer (`#help`)

**Plain-language opening (always visible)**
- **Eyebrow:** Community
- **Heading (h2):** You won't be on your own
- **In short:** Every popular version has a friendly community, and most beginner questions have been answered before. These are good places to ask.

**The details** (none)

| Where | What it's for |
|---|---|
| **Ask Ubuntu** (askubuntu.com) | Questions and answers for Ubuntu and Ubuntu-based distros, including Mint, Pop!_OS and Zorin OS. |
| **Fedora Discussion** (discussion.fedoraproject.org) | The official Fedora community forum. |
| **Linux Mint Forums** (forums.linuxmint.com) | A friendly forum with a dedicated area for newcomers. |
| **Arch Wiki** (wiki.archlinux.org) | Detailed guides that help with almost any distro, not just Arch. |
| **The Omarchy Manual** (learn.omacom.io) | The official guide to Omarchy's keybindings, themes and tools. |
| **r/linux4noobs** (reddit.com/r/linux4noobs) | A Reddit community where beginner questions are welcome. |

### Final call to action
**Heading (h2):** Try Linux this weekend.
**Body:** Pick a distro, put it on a USB stick and start it up. You don't have to install anything until you're sure.
**Button:** Help me choose
**Secondary link:** Read the switching guide

### Sources
**Heading (h2):** Sources
**Intro:** Every figure on this page links to one of the sources below. We check release facts against official announcements first and use news outlets for context.
**Toggle button:** Show all sources / Hide sources
**Group headings:** Official announcements · News and analysis · Gaming data
*(Source list generated from `research/distros-2026.md` §10 and §11.)*

### Footer
**About the name (h3):** About the name
**About the name body:** Distro L. Desk is a nod to Philip K. Dick, who spent a career asking which machines we can trust. We think the answer should include the one on your desk.

**Independence statement:** Distro L. Desk is an independent guide. It is not affiliated with or endorsed by Canonical, the Fedora Project, Red Hat, System76, 37signals, Linux Mint, Debian, SUSE, Valve, Zorin, elementary or the NixOS Foundation.
**Trademark notice:** Linux® is the registered trademark of Linus Torvalds in the U.S. and other countries. All other names are trademarks of their respective owners.
**Updated line:** Last updated September 2026.
**Corrections link:** Spotted a mistake? Email us at [corrections email address] (a `mailto:` link with the subject "Correction: Distro L. Desk")
**Footer navigation:** What's new · Distros · Compare · Find yours · Switch · FAQ · Sources
**Colophon:** Built with plain HTML and CSS, with no trackers and no cookies.
**Copyright:** © 2026 Distro L. Desk

---

## 20. 404 page

**`<title>`:** Page not found · Distro L. Desk
**Heading (h1):** Do androids dream of missing pages?
**Body:** This page doesn't exist, or it has moved. The rest of the desk is still here.
**Button:** Back to the guide
**Secondary link:** Help me choose

---

## 21. Microcopy reference

| Context | Text |
|---|---|
| Expand distro details | More details |
| Collapse distro details | Fewer details |
| Planned release badge | Planned |
| Recheck marker (internal only, never shown) | [S] |
| Copy-link button on section headings (aria) | Copy link to this section |
| Link copied confirmation | Link copied |
| Loading state (if any) | Loading… |
| JavaScript-off note for the finder | The interactive finder needs JavaScript. Here's the same advice as a table. |
| Print header | Distro L. Desk: an independent guide to Linux in 2026 (printed from distroldesk.[tld]) |
