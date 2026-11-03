<div align="center">

<img src="https://raw.githubusercontent.com/agonyG4/AstreaOS/main/gitpage/logo/AstreaOS_landwhite.png" width="420" alt="Astrea logo">

# Astrea

**A modern, native Linux desktop environment built for performance, customization, and a seamless user experience.**

[Typhon](https://github.com/agonyG4/Typhon) · [Eclipse](https://github.com/agonyG4/Eclipse) · [Orbit](https://github.com/agonyG4/Orbit)

</div>

Astrea is an open-source Linux desktop project built around a custom Wayland compositor, a native desktop shell, and an integrated ecosystem of applications.

Rather than building on top of an existing desktop environment, Astrea develops its core components independently, with a focus on performance, visual consistency, responsiveness, and architectural simplicity.

## Architecture

Astrea consists of three primary projects:

### Typhon — Wayland Compositor

[Typhon](https://github.com/agonyG4/Typhon) is a native Wayland compositor written in Rust, responsible for window management, rendering, input handling, and display presentation.

Key capabilities include:

- Native DRM/KMS rendering and display management.
- Dynamic window management and animations.
- Adaptive double and triple buffering.
- Direct scanout and variable refresh rate (VRR).
- Frame scheduling and presentation optimizations.
- GPU-accelerated visual effects.
- XWayland compatibility.

### Eclipse — Desktop Shell

[Eclipse](https://github.com/agonyG4/Eclipse) provides the graphical desktop experience, built primarily with C++ and Qt Quick.

Its components include:

- **Spotlight:** Application launcher and search.
- **Dock:** Application launching and pinned applications.
- **AltTab:** Window switching.
- **Screenshots:** Screenshot interface and configuration.
- **Shared infrastructure:** Application management, desktop integration, and common services.

### Orbit — Native Applications

[Orbit](https://github.com/agonyG4/Orbit) contains Astrea's native application ecosystem, developed primarily with C++, Qt 6, and Rust.

Its main application is **Explorer**, a native file manager designed for efficient filesystem navigation and seamless desktop integration.

Orbit also provides shared UI components, application services, and system integration infrastructure.

## Design Philosophy

Astrea is guided by four principles:

- **Performance:** Minimize unnecessary overhead and prioritize responsiveness.
- **Consistency:** Create a unified experience across the compositor, shell, and applications.
- **Customization:** Give users meaningful control over their desktop environment.
- **Native Integration:** Design components to work together without unnecessary abstraction layers.

## Project Status

Astrea is currently under active development and is not yet intended as a production-ready desktop environment.

The compositor, shell, and applications are maintained in separate repositories:

| Repository | Description |
|---|---|
| [Typhon](https://github.com/agonyG4/Typhon) | Wayland compositor and window manager |
| [Eclipse](https://github.com/agonyG4/Eclipse) | Desktop shell |
| [Orbit](https://github.com/agonyG4/Orbit) | Native applications |
| [AstreaOS](https://github.com/agonyG4/AstreaOS) | Legacy runtime and project entry point |

---

**Astrea — A desktop built from the ground up.**
