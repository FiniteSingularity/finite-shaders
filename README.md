# FiniteSingularity's Shaders

This repo contains a growing set of OBS shaders developed by FiniteSingularity on and for his stream (https://twitch.tv/finitesingularity).

The shaders are broken up by directory indicating the plugin required to use them. Currently, the shaders are only supported in [StreamFX](https://obsproject.com/forum/resources/streamfx-for-obs%C2%AE-studio.578/), however future plans are to also support them in [OBS Shader Filter](https://obsproject.com/forum/resources/obs-shaderfilter.775/).

**NOTE- Current version has only been tested with StreamFX v0.10.1 [here](https://github.com/Xaymar/obs-StreamFX/releases/tag/0.10.1), and may not work with the v0.11 beta.**

## Using the shaders in StreamFX

1. Install StreamFX following the instructions at the link above.
2. Open the "Filters" menu for the source/scene you would like to apply the shader to.
3. Click the + and add a new Shader filter.
4. Click "Browse" in the shader filter panel, and navigate to the `streamfx` directory at the root level of this project. Select the `.effect` file you want to use.
5. Enjoy all of the glorious shader goodness!

## Available Shaders

### hex-transition

This shader creates a customizable hexagon "frosted block" pattern that can sweep over a source, revealing or obsucring it. Combined with the Move Value filter, this can create a very nice animated hide/reveal transition. The adjustable parameters are:

1. **Hexagon Orientation**- Can take the value of `Pointy` or `Flat`. This indicates if the top surface of the repeating hexagons are a corner point, or if they are rotated to have a flat top.
2. **Hexagon Scale**- the number of half-hexagons that tile across the screen for the `Pointy` orientation (so a value of 10 will yield 5 full hexagons). Note, for `Flat` the scaling is slightly different, and so you will get slightly more than a 2-to-1 count of hexagons across the frame.
3. **Make non-hexagon pixels transparent**- When enabled, this will set the alpha of any pixels outside of the hexagons and transition zone to zero, allowing sources behind to show through. This allows the user reveal another source behind the hexagons, or to apply filters underneath the hexagon layer (e.g.- a blur or LUT) that only affect the hexagons themsleves.
4. **Reveal Distance**- a value between `0.0` and `100.0` that specifies how far across the frame the transition wipe currently is. This is the value that would be animated with the `Move Value` filter to animate a wipe on/wipe off transition.
5. **Transition Zone Size**- Width in pixels of the tranzition zone that hexagons appear in, as the reveal distance is changed. Pixels grow from a point in this zone to full-size as the reveal distance moves.
6. **Transition Angle**- An angle between `-180.0` and `180.0` degrees that determines the direction of the transition/reveal. An angle of `0.0` will wipe from left to right, `90.0` will move from bottom to top, etc.
7. **Transition Background Color**- RGBA values for the background of the transition zone. Set the alpha value to zero for no background.

### qbert-transition

This shader creates a customizable Q-Bert 3-D step pattern that can sweep over a source, revealing or obsucring it. Combined with the Move Value filter, this can create a very nice animated hide/reveal transition. The adjustable parameters are:

1. **Scale**- Scaling of the number of steps in the frame. Larger number means more (and thus smaller) scaled steps.
2. **Make non-rhombus pixels transparent**- When enabled, this will set the alpha of any pixels outside of the rhombuses and transition zone to zero, allowing sources behind to show through. This allows the user reveal another source behind the pattern, or to apply filters underneath the pattern layer (e.g.- a blur or LUT) that only affect the steps themsleves.
3. **Reveal Distance**- a value between `0.0` and `100.0` that specifies how far across the frame the transition wipe currently is. This is the value that would be animated with the `Move Value` filter to animate a wipe on/wipe off transition.
4. **Transition Zone Size**- Width in pixels of the tranzition zone that rhombuses appear in, as the reveal distance is changed. Pixels grow from a point in this zone to full-size as the reveal distance moves.
5. **Transition Angle**- An angle between `-180.0` and `180.0` degrees that determines the direction of the transition/reveal. An angle of `0.0` will wipe from left to right, `90.0` will move from bottom to top, etc.
6. **Transition Effect**- Can be either "Blobs" or "Blinds". Blobs are round circles that expand to fill a rhombus giving a "blobby" effect. Blinds are vertical lines that thicken horizontally to fill the rhombuses, giving a vertical blinds effect.
7. **Transition Background Color**- RGBA values for the background of the transition zone. Set the alpha value to zero for no background.

### triakis-transition

This shader creates a customizable Triakis Triangle tessellation (the Disney World Epcot ball pattern) that can sweep over a source, revealing or obsucring it. Combined with the Move Value filter, this can create a very nice animated hide/reveal transition. The adjustable parameters are:

1. **Triangle Scale**- Scaling of the number of pattern repeats in the frame. Larger number means more (and thus smaller) scaled triangles.
2. **Make non-triangle pixels transparent**- When enabled, this will set the alpha of any pixels outside of the triangles and transition zone to zero, allowing sources behind to show through. This allows the user reveal another source behind the pattern, or to apply filters underneath the pattern layer (e.g.- a blur or LUT) that only affect the steps themsleves.
3. **Reveal Distance**- a value between `0.0` and `100.0` that specifies how far across the frame the transition wipe currently is. This is the value that would be animated with the `Move Value` filter to animate a wipe on/wipe off transition.
4. **Transition Zone Size**- Width in pixels of the tranzition zone that triangles appear in, as the reveal distance is changed. Pixels grow from a point in this zone to full-size as the reveal distance moves.
5. **Transition Angle**- An angle between `-180.0` and `180.0` degrees that determines the direction of the transition/reveal. An angle of `0.0` will wipe from left to right, `90.0` will move from bottom to top, etc.
6. **Transition Effect**- Can be either "Blobs" or "Blinds". Blobs are round circles that expand to fill a rhombus giving a "blobby" effect. Blinds are vertical lines that thicken horizontally to fill the rhombuses, giving a vertical blinds effect.
7. **Transition Background Color**- RGBA values for the background of the transition zone. Set the alpha value to zero for no background.
