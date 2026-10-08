---
name: flow-diagrammer
description: Convert complex explanations, processes, algorithms, and system protocols into clear text diagrams, Mermaid charts, sequence flows, and ASCII schemas instead of walls of text. Use when asked to draw a diagram, visualize a flow, create a sequence chart, or explain with schemas instead of text.
---
# Flow Diagrammer (Text to Diagram)

Converts conceptual explanations and multi-step processes into intuitive, visually structured Mermaid and ASCII diagrams, replacing dense paragraphs with instant visual clarity.

## When to Use

- When the user asks to explain a process with diagrams or schemas instead of prose ("draw a diagram instead of writing")
- When explaining protocol handshakes (e.g. OAuth2, OIDC, TLS, WebSocket handshakes)
- When mapping user journeys, decision trees, or lifecycle states
- When illustrating distributed component interactions and data pipelines

## Diagram Strategy

### 1. Sequence Diagrams
- Use for multi-party communication (e.g. Browser <-> App Server <-> Identity Provider).
- Clearly separate Front Channel (browser-mediated) and Back Channel (server-to-server direct) interactions.
- Label each arrow with the exact payload or HTTP verb (e.g. `POST /token {code, verifier}`).

### 2. Flowcharts & Decision Trees
- Use for branching logic, conditional retries, and fallback handling.
- Keep node labels concise (under 5 words).

### 3. ASCII / Text Layouts
- Provide ASCII architecture diagrams when terminal or plain-text environments cannot render Mermaid markdown directly.

## Workflow Steps

1. Identify all participating entities (Client, Frontend, Gateway, Microservice, Database, External API).
2. Trace the chronological step-by-step path of data or control.
3. Generate standard Mermaid code blocks (using `sequenceDiagram`, `flowchart TD/LR`, or `stateDiagram-v2`).
4. Annotate critical checkpoints (such as validation, encryption, state verification) directly on the diagram.
5. Provide a short, bulleted 1-sentence explanation for each key step under the diagram.

## Gotchas

- Avoid cluttering a single diagram with more than 6-7 actors; group subsystems or break into sub-diagrams if needed.
- Always include error and failure branches, not just the happy path.
