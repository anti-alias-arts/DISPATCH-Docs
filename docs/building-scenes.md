# Building Scenes

A scene is an ordinary TouchDesigner network inside a COMP. It doesn't need anything from DISPATCH: no special expressions, parameters or helper operators. A scene you build for DISPATCH works the same way in any TouchDesigner project.

## Out Operators

A scene shares its outputs through Out operators at the top level of its COMP. DISPATCH finds them by name.

- Name the main output `out1`. Output groups look for `out1` by default.
- Give other outputs clear names, such as `out_dmx` or `out_laser`, and enter that name in the group or output that should use it.

> **TODO (Jack): screenshot of a minimal scene network with out1.**

## Custom Parameters

Custom parameters on the scene COMP appear in the **Parameters** panel, and can be keyframed on the timeline and driven by macros.

> **TODO (Jack): which parameter types are supported, and a tip on promoting parameters from inside the network.**

## Performance

> **TODO (Jack): scenes are paused and their textures unloaded when they aren't running, so don't rely on a scene keeping state while it's off. Tips on keeping scenes light.**
