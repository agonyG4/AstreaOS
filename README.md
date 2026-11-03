<div align="center">

<img src="https://raw.githubusercontent.com/agonyG4/AstreaOS/main/gitpage/logo/AstreaOS_landwhite.png" width="420" alt="Astrea logo">

# Astrea

**A native Linux desktop for people — designed with autonomous agents in mind.**

[Typhon](https://github.com/agonyG4/Typhon) · [Eclipse](https://github.com/agonyG4/Eclipse) · [Orbit](https://github.com/agonyG4/Orbit)

</div>

> [!IMPORTANT]
> **Astrea is under active development and is not a production-ready desktop distribution.**
>
> This repository preserves the legacy AstreaOS distribution/runtime and serves as the project's entry point. The active desktop architecture lives in the repositories linked above. Consult their documentation for current build requirements and behavior.

## Overview

Astrea is a Linux desktop project built around a native Wayland compositor, a dedicated desktop shell, and a suite of native applications. It aims to feel like a complete, customizable desktop for everyday use while laying the groundwork for a different kind of computing: humans and autonomous software agents operating in the same environment without fighting for control of the same screen or input devices.

The immediate priority is a reliable traditional desktop. Agent-native capabilities are a **long-term architectural direction**, not a feature currently available to end users.

## Architecture

| Component | Responsibility | Current implementation |
| --- | --- | --- |
| **[Typhon](https://github.com/agonyG4/Typhon)** | Wayland compositor and window manager | Rust; native seat and DRM/KMS session, window management, rendering, input, presentation scheduling and XWayland integration |
| **[Eclipse](https://github.com/agonyG4/Eclipse)** | Desktop shell | Qt Quick / C++; Spotlight launcher, Alt-Tab switcher, Dock foundation, shared application-launching infrastructure and screenshot customization work |
| **[Orbit](https://github.com/agonyG4/Orbit)** | Native applications and shared UI infrastructure | Qt 6 / C++ Explorer with Rust filesystem and integration components, file chooser portal, shared QML modules and tests |
| **[AstreaOS](https://github.com/agonyG4/AstreaOS)** | Legacy runtime and project entry point | Preserved distribution/runtime code; not the source of truth for the new desktop |

### Typhon — the graphical foundation

Typhon is a native Wayland compositor, built in Rust. It owns the Wayland server, scene and window lifecycle, rendering, native input, and presentation to the display.

Current engineering areas include:

- Native DRM/KMS startup, with Atomic KMS preferred and defined fallbacks.
- Dynamic window management, fullscreen transitions, decorations and animations.
- Deadline-aware frame presentation, dedicated KMS commit work and adaptive double/triple buffering.
- Validated primary-plane direct scanout and capability-gated VRR, tearing and hardware-cursor paths.
- Damage-aware effects, blur and rendering optimizations.
- Managed XWayland support for applications that need it.

Typhon currently targets a **single display output**. Multi-output layout and hotplug, multi-GPU operation, and HDR are not supported; color management is limited to sRGB. Some optimizations depend on driver and hardware support and may fall back safely.

Read the [Typhon README](https://github.com/agonyG4/Typhon#readme), [native session guide](https://github.com/agonyG4/Typhon/blob/main/docs/NATIVE_SESSION.md), and [known issues](https://github.com/agonyG4/Typhon/blob/main/docs/KNOWN_ISSUES.md) for supported configuration, launch commands, and limitations.

### Eclipse — the desktop experience

Eclipse provides Astrea's user-facing shell through native Qt Quick components. Its codebase includes:

- **Spotlight:** launcher and application search.
- **AltTab:** window-switching interface and application identity resolution.
- **Dock:** a Layer Shell-based foundation for pinned application launching.
- **Shared infrastructure:** supervised application launching, desktop-entry catalog and icon services.
- **Screenshot UI:** customization and capture lifecycle work.

The Dock is still foundational: Typhon does not yet expose the public window-management protocol needed to report running, focused, or minimized app state, so Eclipse does not pretend those integrations are finished.

See [Eclipse](https://github.com/agonyG4/Eclipse) for current prerequisites and implementation status.

### Orbit — native applications

Orbit hosts Astrea's native application stack. Its current production application is **Explorer**, a Qt 6/C++ file manager with Rust-backed filesystem and integration components. The repository also contains the file chooser portal, application-launching services, shared QML components, localization infrastructure, and qualification tests.

Legacy applications are preserved under `old/` and are not part of the active build. See the [Orbit README](https://github.com/agonyG4/Orbit#readme) and its [architecture documentation](https://github.com/agonyG4/Orbit/blob/main/docs/ARCHITECTURE.md).

## Agent-native vision

Astrea is exploring an **Agent Control Plane** integrated into the operating environment instead of bolting a chatbot or screen-clicking automation tool onto a desktop.

The proposed direction includes persistent agent identities and tasks, agent-owned or shared workspaces, independent logical input seats, headless or virtual graphical sessions, semantic access to windows and applications, capability-based permissions, auditable actions, and explicit human control. Conventional UI automation would remain a fallback where a native API or semantic interface is unavailable.

**These are design goals, not claims of shipping functionality.** The traditional human-operated desktop remains the foundation.

## Development status

Astrea is an experimental, multi-repository project. The active components are built and tested independently, and their integration is still evolving. There is no supported one-command install or stable end-user release documented here.

If you want to work with the current code, start with the component repository relevant to your changes:

- **Compositor, rendering or presentation:** [Typhon](https://github.com/agonyG4/Typhon)
- **Desktop shell or launcher:** [Eclipse](https://github.com/agonyG4/Eclipse)
- **Explorer, native apps or shared QML:** [Orbit](https://github.com/agonyG4/Orbit)

Follow each repository's build instructions rather than using legacy AstreaOS runtime scripts as documentation for the current architecture.

## Philosophy

A desktop should remain fast, predictable and useful without AI. Windows, keyboard and mouse input, application launching, customization, and familiar workflows come first.

Astrea's longer-term bet is that personal computers can support more than one kind of operator — with clear boundaries between human authority and autonomous work.

**A desktop for humans. An architecture ready to evolve beyond human-only interaction.**
