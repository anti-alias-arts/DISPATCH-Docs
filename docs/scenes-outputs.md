# Scenes & Outputs

## Scenes

A scene is any TouchDesigner network: video, DMX, lasers, audio or data. It shows on the grid as a tile.

### Adding Scenes

> **TODO (Jack): from Assets, from a .tox file, new empty network from a template.**

### What Runs When

Only scenes that are live, transitioning in, or toggled on are running. Every other scene is paused and its textures are unloaded, so a large show doesn't fill your GPU memory.

> **TODO (Jack): note the preload time (Settings > Performance) for timeline cues.**

## Output Groups

An output group plays one scene at a time and transitions between them. Each of its outputs takes its own operator from the scene and transitions it in its own way:

| Output type | Transition |
|---|---|
| TOP (video) | Crossfade over the output's own **Transition** time, at its own **Width** × **Height** |
| POP (points, lasers) | Blend between point sets over the output's own **Transition** time |
| CHOP, SOP or DAT (data, DMX, messages) | Switches at the start of the Go, never crossfades |

A Go is finished when the longest transition in the group ends.

!!! note
    DISPATCH doesn't layer scenes. For layered video, send to AAVJ.

### Adding and Editing Groups

The **Output Groups** panel lists every group. Each row shows the group's colour, its name and one small square per output, coloured by output type.

- **Add a group:** press **+**. The group opens straight away in the output group window.
- **Edit a group:** click its pencil icon.
- **Reorder groups:** drag a group by its name onto another group. It takes that group's place; a grey line shows where it will land.
- **Turn a group's outputs on or off:** press the power button. Green means all of its outputs are on, amber means some are and grey means none are.
- **Remove a group:** press **×**, then press **Delete?** to confirm. Its outputs are removed with it.

### The Output Group Window

The output group window opens as its own window, on top of DISPATCH, so you can move it anywhere, even when DISPATCH only fills part of the screen. Changes in the window take effect as you make them.

The top row holds the group's **Name** and **Color**. The colour shows in the panel and on the group's tiles.

Below that, the group's outputs are listed on the left. Click one to edit it on the right, press **+** to add one, or press its **×** twice to remove it.

The right column holds the selected output's settings:

- **Output Format** and **Output Method**: what kind of output it is, and how it's sent.
- **Out Op**: the operator name it takes from each scene (`out1` by default).
- **Name**
- **Transition (s)**: in seconds, 1 s by default. 0 is a cut. Only shown for video and points outputs.
- **Width** and **Height**: the size of the crossfade, 1920 × 1080 by default. Only shown for video outputs.
- The device's own settings.

When you close the window:

- **Done**, **×**, **Esc** or the window's close button keeps everything.
- **Cancel** is only there for a group you've just added. It removes the new group and its outputs again.

> **TODO (Jack): screenshot of the Output Groups panel and the output group window.**

## Outputs

An output sends something from a group's live scene to a device. Each output names the operator it reads. Add and edit outputs in the output group window.

> **TODO (Jack): the output types (NDI, Syphon/Spout, video device, Touch Out, DMX, OSC, MIDI). Explain the send methods in user terms: in, chop, fixture, par.**

Under the output's settings, the device's main controls come first: usually **Active**, the address and the port. Everything else (frame rate, serial port, KiNET, multicast and so on) is folded under **Advanced**. Click **Advanced** to show or hide it.

### Screen Output

> **TODO (Jack): sending a group to a display.**
