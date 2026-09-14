# Shared XR workflow

Use this guide for XR projects. Read the game's `docs/xr-setup.md` and game brief before applying it. Project-specific instructions override these defaults. For non-XR projects, skip this guide.

## Find the project and tools

- Confirm the intended Unity project, scene, and running target before acting, especially when multiple Editor instances or devices are connected.
- Discover the tools and resources actually exposed by the connected MCP servers. Use their current schemas; do not invent tool names, arguments, or successful results.
- Check the project's installed Unity, OpenXR, and Meta SDK versions and its chosen interaction framework. Do not assume every game uses the same rig, locomotion, or input bindings.
- These Markdown documents do not install packages, enable OpenXR features, or connect MCP servers. If a required connection is unavailable, explain what is missing and continue any independent work.

## Choose the tool for the action

**Unity MCP (CoplayDev):** use the Editor integration to inspect and edit scenes, GameObjects, components, assets, and scripts, and use the available Editor, console, and test controls. Inspect existing project structure before modifying it. Check compilation and relevant console errors after changes.

**Meta XR Operator:** use the connected running OpenXR app to observe XR session state and spatial context, inspect supported scene/UI information, control head and controller poses, send controller input, and capture the result. It is intended for agent-driven development and testing. Use only capabilities advertised by the installed version.

Use Editor tools to prepare and inspect the game, and XR Operator for player-style XR interaction where supported. Directly changing transforms or invoking a custom shortcut does not verify that the normal player interaction works.

## Run an interaction check

1. Read the relevant level/mechanic brief and define the expected observable result.
2. Confirm the target environment: Editor/Simulator, Quest Link, or an on-device Quest build. Start from the project's documented test scene and reset state.
3. Inspect the active XR session, rig, input mode, and tracking origin. Check units and coordinate conventions before applying poses; do not interchange Unity and OpenXR coordinates without the appropriate conversion.
4. Perform a small, controlled sequence using the documented player inputs. Observe state and captures between actions, and release held buttons/triggers afterward. Reset overridden poses/input when the tools support it.
5. Compare the observed behavior against the expected result. Check relevant console errors with Unity MCP when the Editor is available; use the project's device logging workflow for standalone builds.
6. Record the environment, scene, steps, expected/actual result, and available evidence in the game's playtest or QA notes. Restore the agreed test state.

Do not claim a test passed when a connection failed or an action could not be observed. Label custom-tool or simulated shortcuts explicitly.

## XR design and verification checks

- Bob and the game designer: check player scale, reach, sightlines, interaction distance, and the game's seated/standing and locomotion requirements.
- Fox and the tools developer: follow the actual rig and input architecture; preserve tracking behavior and verify changes through the player interaction path.
- Technical artist: check visual readability and measure against the project's target-device performance budgets.
- Audio designer: check spatial cues and their behavior as the player turns or moves.
- Narrative and economy designers: make prompts, choices, rewards, and feedback usable through the project's XR interactions.
- QA: cover the project's supported input modes, reset/re-entry paths, and relevant boundary conditions.

Editor/Simulator results establish only what was checked in that environment. Headset comfort, physical reach, tracking quality, and on-device performance require appropriate headset measurements or human playtesting. Mark these as unverified when that evidence is unavailable. Do not invent universal frame-rate, reach, or comfort thresholds; use the project setup and brief.

## Compatibility and references

Meta describes XR Operator as experimental; APIs and behavior can change. Keep it as development/test tooling, and check current Meta guidance before including it in a distributed build. Record actual project versions and connection details in the game, not in this shared library.

As of the documentation check on 2026-09-14, Meta lists Windows with Quest Link/Simulator, Apple Silicon macOS with Simulator, and on-device Quest workflows. On-device connections require the documented ADB forwarding setup. Confirm current support before configuring a new environment.

- [Meta XR Operator overview and setup links](https://developers.meta.com/horizon/documentation/unity/meta-xr-operator/)
- [Unity MCP installation and available capabilities](https://github.com/CoplayDev/unity-mcp)

References checked: 2026-09-14. Live tool schemas and the project's installed versions determine available operations.
