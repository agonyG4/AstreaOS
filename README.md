<div align="center">

<img src="https://raw.githubusercontent.com/agonyG4/AstreaOS/main/gitpage/logo/AstreaOS_landwhite.png" width="420">

# Astrea

**A Linux desktop environment being designed for both humans and autonomous AI agents.**

</div>

> [!IMPORTANT]
> This repository contains the legacy AstreaOS distribution/runtime code and is **not the authoritative source for the current desktop architecture**.
>
> Current development is centered around **Typhon**, the custom Wayland compositor, and **Eclipse**, the desktop shell.

## Current project

Astrea is evolving into a highly customizable Linux desktop that remains a complete traditional desktop environment while being designed from the start for a future where autonomous agents can also operate and work on the same computer.

The goal is not to place an AI chatbot on top of a desktop. Astrea is exploring a system where humans and agents can coexist as independent operators: a person can continue using the computer normally while agents can have persistent tasks, workspaces, applications, permissions, and eventually headless or virtual graphical environments of their own.

### Typhon

[Typhon](https://github.com/agonyG4/Typhon) is Astrea's custom native Wayland compositor and window manager. It currently owns the Wayland server and native DRM/KMS session and includes work on window management, dynamic tiling, rendering and effects, frame presentation, lifecycle handling, input, and XWayland integration.

### Eclipse

[Eclipse](https://github.com/agonyG4/Eclipse) is Astrea's desktop shell. It provides the user-facing desktop experience and is intended to remain highly customizable while integrating tightly with Typhon.

## Agent-native direction

The next architectural direction is an **Agent Control Plane** built into the operating environment rather than added as an external automation layer.

Areas being designed include:

- persistent agent identities and tasks;
- agent-owned or shared workspaces;
- logical agent input seats that do not compete with the human cursor;
- headless and virtual graphical workspaces;
- semantic control of windows, applications, and system state;
- capability-based permissions and explicit human authority;
- auditable agent actions;
- UI automation as a fallback when native semantic or API control is unavailable.

This agent runtime is currently a **design direction and active area of development**, not a completed production feature.

## Philosophy

Astrea is intended to work as a normal desktop first: keyboard, mouse, floating windows, dynamic tiling, applications, customization, panels, launchers, and the rest of the traditional desktop experience remain fundamental.

The difference is architectural: Astrea is being built with the assumption that, in the future, humans may not be the only actors using a personal computer.

**Humans use the computer. Agents can work on it too.**

## Active repositories

- [Typhon](https://github.com/agonyG4/Typhon) — Wayland compositor and window manager
- [Eclipse](https://github.com/agonyG4/Eclipse) — desktop shell
- [AstreaOS](https://github.com/agonyG4/AstreaOS) — legacy distribution/runtime repository and project entry point
