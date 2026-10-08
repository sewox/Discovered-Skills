---
name: disposable-web-artifact
description: Generate self-contained, interactive single-file HTML/CSS/JS artifacts that visually simulate multi-step processes, protocols, workflows, and algorithms with interactive controls. Use when asked to create an interactive web page, HTML simulation, clickable step-by-step explainer, or disposable artifact to understand a topic.
---
# Disposable Web Artifact (Interactive Simulation)

Creates complete, self-contained single-file HTML/CSS/JS artifacts that turn abstract multi-step concepts into interactive, clickable simulations ("use & discard" interactive visualizers).

## When to Use

- When the user asks for an interactive web page, artifact, or visual simulator to learn or inspect a process
- When explaining complex multi-stage protocols (OAuth2 handshake, TLS negotiation, 2PC transactions, consensus algorithms)
- When static text or diagrams are insufficient and the user needs interactive step-by-step controls (Play, Pause, Step Next, Inspect State)
- When a lightweight, disposable prototype or educational tool is needed instantly without external dependencies

## Architecture of the Artifact

### 1. Single-File Self-Contained Design
- All code (HTML5 markup, modern CSS styling, and Vanilla JavaScript) must reside in a single standalone file.
- Zero external dependencies: no external CDNs, frameworks, or fonts that require internet access. Use system fonts (system-ui, -apple-system, sans-serif) and inline SVG icons.

### 2. Interactive Components
- **Step Controller:** Clear "Previous", "Next", and "Reset" buttons, plus a progress bar or step indicators (e.g. "Step 3 / 12").
- **Visual Stage:** An animated or highlighted area displaying current actors, active channels, and passing data packets.
- **Inspector Panel:** Collapsible panels displaying raw headers, payloads (JSON/HTTP/SQL), token parameters, and state variables for the current step.
- **Channel Legend:** Distinguish Front Channel vs Back Channel, client-side execution vs server-side execution.

## Workflow Steps

1. Break the process down into discrete, numbered logical phases (typically 6-12 steps).
2. Define the exact state, message payload, and active participants for each phase.
3. Write clean, accessible semantic HTML with dark/light mode friendly styling.
4. Implement reactive DOM updates in vanilla JS attached to step navigation.
5. Provide the code ready to be rendered in an artifact window or saved locally to inspect in any browser.

## Gotchas

- Do not use external network assets (images or CDN scripts) that fail in offline/sandboxed environments.
- Ensure state reset and reverse navigation work seamlessly without corrupting state values.
