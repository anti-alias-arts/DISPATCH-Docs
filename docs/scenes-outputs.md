# Scenes & Outputs

## Scenes

A scene is any TouchDesigner network: video, DMX, lasers, audio or data. It shows on the grid as a tile.

### Adding Scenes

> **TODO (Jack): from Assets, from a .tox file, new empty network from a template.**

### What Runs When

Only scenes that are live, transitioning in, or toggled on are running. Every other scene is paused and its textures are unloaded, so a large show doesn't fill your GPU memory.

> **TODO (Jack): note the preload time (Settings > Performance) for timeline cues.**

## Output Groups

An output group plays one scene at a time and transitions between them.

Each group names the operator it takes from the live scene, `out1` by default. What kind of operator it finds decides how the group transitions:

| Operator | Transition |
|---|---|
| TOP (video) | Crossfade |
| POP (points, lasers) | Blend between point sets |
| CHOP or DAT (data, DMX) | Switches at the start of the Go, never crossfades |

!!! note
    DISPATCH doesn't layer scenes. For layered video, send to AAVJ.

### Group Settings

Set these in the **Outputs** panel:

- **Out op**: the operator name to take from each scene (`out1` by default).
- **Transition time**: in seconds, 1 s by default. 0 is a cut.
- **Resolution**: 1920 × 1080 by default.

> **TODO (Jack): adding, colouring and removing groups. Screenshot of the Outputs panel.**

## Outputs

An output sends something from a group's live scene to a device. Each output names the operator it reads.

> **TODO (Jack): adding an output, and the output types (NDI, Syphon/Spout, video device, Touch Out, DMX, OSC, MIDI). Explain the send methods in user terms: in, chop, fixture, par.**

### Screen Output

> **TODO (Jack): sending a group to a display.**
