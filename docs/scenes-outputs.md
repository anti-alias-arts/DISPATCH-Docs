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

### Adding and Editing Groups

The **Output Groups** panel lists every group. Each row shows the group's colour, its name and one small square per output, coloured by output type.

- **Add a group:** press **+**. The group opens straight away in the output group window.
- **Edit a group:** click its name or the pencil icon.
- **Turn a group's outputs on or off:** press the power button. Green means all of its outputs are on, amber means some are and grey means none are.
- **Remove a group:** press **×**, then press **Delete?** to confirm. Its outputs are removed with it.

### The Output Group Window

Changes in the window take effect as you make them.

The top of the window holds the group's settings:

- **Name**
- **Out Op**: the operator name to take from each scene (`out1` by default).
- **Transition (s)**: in seconds, 1 s by default. 0 is a cut.
- **Width** and **Height**: 1920 × 1080 by default.
- **Color**: the group's colour in the panel and on its tiles.

Below the settings, the group's outputs are listed on the left. Click one to edit it on the right, press **+** to add one, or press its **×** twice to remove it.

When you close the window:

- **Done**, **×**, **Esc** or a click outside the window keeps everything.
- **Cancel** is only there for a group you've just added. It removes the new group and its outputs again.

> **TODO (Jack): screenshot of the Output Groups panel and the output group window.**

## Outputs

An output sends something from a group's live scene to a device. Each output names the operator it reads. Add and edit outputs in the output group window.

> **TODO (Jack): the output types (NDI, Syphon/Spout, video device, Touch Out, DMX, OSC, MIDI). Explain the send methods in user terms: in, chop, fixture, par.**

Under the output's settings, the device's main controls come first: usually **Active**, the address and the port. Everything else (frame rate, serial port, KiNET, multicast and so on) is folded under **Advanced**. Click **Advanced** to show or hide it.

### Screen Output

> **TODO (Jack): sending a group to a display.**
