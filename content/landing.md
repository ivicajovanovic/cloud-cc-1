# Landing page: structure and copy (draft 1)

**Working name:** *Distro Desk*. This is a placeholder; replace it if you have a name or domain.
**What the site is:** an independent guide to the Linux releases that matter in 2026, and help choosing one.
**Main visitor action:** find a distro that fits → go to its official download page.
**Secondary action:** read what changed in 2026.
**Voice:** plain, specific, friendly to newcomers but accurate enough for experienced users. No hype words, no invented numbers, no fake testimonials. Every fact comes from `research/distros-2026.md`.

**Creative concept, "the desk":** the page is a physical control desk made of the soft material from `design.md`. Distros are **keycaps** you press. The distro finder is a row of **switches**. The 2026 timeline is a **dial or slider** you scrub through. This uses skeuomorphism where it helps people understand the controls: pressing, switching, turning.

---

## 0. Head / SEO

- `<title>`: Distro Desk: the Linux releases that matter in 2026
- Meta description: Ubuntu 26.04 LTS, Omarchy 4, Fedora 44, COSMIC and more, explained plainly. See what changed in Linux this year and find the distro that fits how you work.
- Social image: the hero keycap row on the soft surface, 1200×630.

---

## 1. Navigation

Logo/wordmark · What's new · Distros · Find yours · Try it safely · FAQ
Theme switch (light/dark) drawn as a real toggle.

---

## 2. Hero

**Eyebrow:** Linux in 2026

**Headline:** Linux had a big year. Pick the version that fits you.

**Subhead:** Ubuntu went Wayland-only, Omarchy rebuilt its whole desktop, and Rust moved into the kernel and core tools. Here is what changed, and which distro suits how you work.

**Primary button:** Find your distro → (#finder)
**Secondary button:** See what changed → (#whats-new)

**Visual:** a row of large soft keycaps, one per distro (monogram + name: Ubuntu, Omarchy, Fedora, Pop!_OS, Mint, Debian). Pressing one sinks it (inset shadow) and scrolls to that distro's card. Use text monograms instead of official logos until trademark use is cleared (see §10).

---

## 3. What changed in 2026 (#whats-new)

**Heading:** Six changes that matter this year

1. **Wayland is the default now.** Ubuntu 26.04 removed the GNOME-on-X11 session. Linux Mint is bringing Wayland to Cinnamon. Old X11 apps still run through XWayland.
2. **Rust moved into the core.** Rust support in Linux 7.0 is no longer experimental. Ubuntu ships `sudo-rs` and Rust coreutils by default, and System76's COSMIC desktop is written entirely in Rust.
3. **Encryption uses your hardware.** Ubuntu 26.04 supports full-disk encryption backed by the TPM chip.
4. **Image-based systems grew up.** Fedora Atomic and Bazzite update the whole system in one step, and you can roll back if something breaks.
5. **Gaming keeps getting easier.** Fedora 44 adds NTSYNC for Wine and Steam. Bazzite comes ready for Steam with drivers installed.
6. **AI agents on the desktop.** Omarchy 4 lets you pick a default coding agent (Claude Code, Codex, Gemini and others) as part of setup.

(Design note: six flat items in a two-column grid, each with a small icon. Don't make them six identical raised cards.)

---

## 4. Timeline (#timeline)

**Heading:** The 2026 release calendar

Interactive slider/dial. Each stop shows a date and one line:

- **Apr 12:** Linux 7.0. Rust support is no longer experimental; self-healing XFS arrives.
- **Apr 23:** Ubuntu 26.04 LTS "Resolute Raccoon". GNOME 50, Wayland-only, supported until 2031.
- **Apr 28:** Fedora 44. GNOME 50, DNF5, GCC 16, NTSYNC for gaming.
- **Jul 1:** COSMIC 1.2. System76's Rust desktop keeps improving. *(check the date)*
- **Aug 14:** Omarchy 4 "Quattro". A new Quickshell desktop, 24-color themes, under-6 GB ISO.
- **Sep 12:** Debian 13.7. The latest point release of stable "trixie".
- **December (planned):** Linux Mint 23 on Ubuntu 26.04, with Wayland for Cinnamon.

---

## 5. Featured distros (#distros)

**Heading:** The distros worth a look right now

Each card has: name + version, a one-line summary, "Good for", 3 facts, and an **Official site →** button. Cards are raised. The selected card is inset.

### Ubuntu 26.04 LTS
*The dependable default, supported until 2031.*
Good for: first-time Linux users, work laptops, servers.
- GNOME 50 on Wayland, Linux 7.0
- TPM-backed full-disk encryption
- 5 years of standard support
→ ubuntu.com/download

### Omarchy 4 "Quattro"
*A finished keyboard-driven desktop for developers.*
Good for: developers and terminal users who want a tiling setup that already looks good.
- Arch Linux + Hyprland, created by DHH
- A new Quickshell desktop: one menu on Super + Space
- Choose a default coding agent at setup; dual-boot and factory reset included
→ omarchy.org

### Fedora 44
*The latest stable software, close to upstream.*
Good for: developers, and anyone who wants new GNOME and KDE releases soon after they ship.
- GNOME 50 Workstation; KDE with the new Plasma Login Manager
- DNF5, GCC 16, LLVM 22
- NTSYNC for better Wine and Steam performance
→ fedoraproject.org

### Pop!_OS 24.04 with COSMIC
*A tiling-friendly desktop written in Rust.*
Good for: people who want tiling without editing config files; NVIDIA users.
- COSMIC desktop, written from scratch in Rust
- Tile windows with the mouse or keyboard
- Flexible workspaces and automatic HiDPI scaling
→ system76.com/pop

### Linux Mint
*The gentlest move from Windows.*
Good for: people switching from Windows, older computers, family PCs.
- A familiar Cinnamon desktop
- Mint 23 planned for December 2026 on Ubuntu 26.04
- New installer and Wayland support planned
→ linuxmint.com

### Debian 13 "trixie"
*A stable foundation many distros build on.*
Good for: servers, and people who prefer predictability to the newest versions.
- Full support until August 2028, LTS until June 2030
- Latest point release: 13.7
- Debian 14 "forky" is planned for 2027
→ debian.org

**For gamers** (smaller row below): **Bazzite** (Fedora Atomic, Steam and drivers ready, easy rollback) → bazzite.gg · **CachyOS** (Arch-based, tuned for performance) → cachyos.org

---

## 6. Distro finder (#finder)

**Heading:** Find yours in three switches

**Intro:** Answer three questions. There's no wrong answer, and you can try another distro later.

1. **How much do you want to tinker?** · Not at all / A little / I enjoy it
2. **What will you mostly do?** · Everyday work / Code / Games / Servers
3. **How do you like to work?** · Mouse and windows / Keyboard and tiling

**Result card:** the suggested distro + one sentence why + Official site button + "Or try: [second choice]".

Suggested mapping (static JS, no tracking):
| Answers | Suggestion | Also try |
|---|---|---|
| Not at all + Everyday | Linux Mint | Ubuntu |
| Not at all / A little + Everyday + mouse | Ubuntu | Mint |
| Code + keyboard/tiling | Omarchy | Pop!_OS |
| Code + mouse | Fedora | Ubuntu |
| Any + Games, low tinkering | Bazzite | Pop!_OS |
| Games + enjoys tinkering | CachyOS | Bazzite |
| Servers | Debian | Ubuntu Server |
| Mouse + wants tiling | Pop!_OS (COSMIC) | Fedora |

---

## 7. Try it safely (#try)

**Heading:** Try Linux without risking your current system

1. **Run it from a USB stick.** Write the ISO to a USB drive with a tool like Fedora Media Writer, balenaEtcher or Ventoy, and boot a live session. Nothing is installed.
2. **Try it in a virtual machine.** GNOME Boxes, VirtualBox or VMware let you test a distro in a window.
3. **Dual-boot when you're ready.** Keep your current system and choose which one to start. Back up first. (Omarchy 4's installer now supports dual boot.)

**Note:** Always download from the official site and check the ISO checksum.

---

## 8. FAQ (#faq)

**What is a Linux distro?**
The Linux kernel plus everything around it: desktop, apps, installer, updates. Different distros make different choices, which is why they feel different.

**Which one should a beginner pick?**
Linux Mint or Ubuntu 26.04 LTS. Both have large communities, graphical app stores and long support.

**What does "LTS" mean?**
Long-term support. Ubuntu 26.04 LTS gets standard updates for five years, until April 2031.

**Will my apps and games work?**
Many do: browsers, Office alternatives, Spotify, VS Code, Steam. A lot of Windows games run through Proton. Check specific apps before you switch.

**What is Wayland and should I care?**
Wayland is the modern way Linux draws windows on screen, replacing X11. It gives smoother graphics and better security. Most apps just work, and older ones run through XWayland.

**Is Omarchy for beginners?**
Not really. It's keyboard-driven and built on Arch. It suits people who like the terminal. Beginners should start with Mint, Ubuntu or Pop!_OS.

**Is this site affiliated with any of these projects?**
No. This is an independent guide. Always download from the official sites linked above.

---

## 9. Final call to action

**Heading:** Pick a distro and try it this weekend.
**Button:** Find your distro → (#finder)

---

## 10. Footer

- "Distro Desk is an independent guide and is not affiliated with Canonical, the Fedora Project, System76, 37signals, Linux Mint or Debian."
- "Linux® is the registered trademark of Linus Torvalds in the U.S. and other countries. Other names are trademarks of their respective owners."
- Sources link → a short sources list (from research §10).
- "Last updated: September 2026."

---

## Open items before building
- [ ] Final site name and domain
- [ ] Decide whether to use official logos (check each project's trademark policy) or keep text monograms
- [ ] Screenshots: take from official press kits or make our own in a VM. Don't hotlink.
- [ ] Recheck every *Secondary* fact in the research file on the official site
- [ ] Update the "Linux Mint 23" card once it ships (planned December 2026)
