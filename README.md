# Verdant Plains: Unity version (C#, runs in the browser via WebGL)

The whole map is generated from C# code when the game starts: terrain, rivers, Greenhaven, the four zones, trees, grass, houses and props. There are no models or textures to import; even the painted textures are made by code.

## What you need
- **Unity 2022.3 LTS or Unity 6**, installed with Unity Hub
- The **WebGL Build Support** module. In Unity Hub go to *Installs*, click the cog next to your version, choose *Add modules*, then *WebGL Build Support*.

## Setup (about 5 minutes)
1. In Unity Hub click **New project** and pick the **3D (Built-In Render Pipeline)** template.
   Don't pick "Universal 3D" or "URP", or the custom shaders will show up pink.
2. Close Unity. Copy the `Assets/VerdantPlains` folder from this zip into your new project's `Assets` folder.
3. Open the project again and wait for it to finish importing.
4. In the top menu bar click **Verdant Plains → 1. Set Up Project**.
   This creates the scene, switches to WebGL and turns on the settings the shaders need.
5. Press **Play** to fly around inside Unity, **or**
6. Click **Verdant Plains → 2. Build WebGL and Open in Browser**.
   Unity compiles to WebAssembly and opens the game in your browser. The first build takes several minutes.

The finished web build is in `Builds/VerdantPlainsWebGL`. Upload that folder to itch.io (as an HTML game) or any web host to share it.

## Controls
Click to capture the mouse, then:
- **WASD** move
- **Mouse** look
- **Space** up, **C** down
- **Shift** fast
- **G** toggle shadows (helps on slow computers)
- **Esc** release the mouse

## What's in it
- **Greenhaven:** plaza fountain, market stalls, 2–4 floor timber-framed houses with stone bases, tiled roofs, lit windows, lamps and banners.
- **Green Fields (Lv 1–3):** fenced wheat, cabbage and pumpkin farms, scarecrows, haystacks, windmills, streams with stone bridges, abandoned farmhouses.
- **Western Grasslands (Lv 3–5):** bigger hills, rocks, goblin camps, abandoned merchant carts.
- **Whispering Woods (Lv 5–7):** dense tall trees, darker fog, glowing mushrooms, fallen logs, clearings with hunting cabins.
- **Forgotten Hills (Lv 7–10):** stepped cliffs, narrow paths, caves, ruins, walled goblin camps, underground entrances.
- **Style:** anime two-tone shading with rim light, a painted sky with drifting clouds, snowy mountains in the distance, and swaying grass and trees.

## Files
- `Scripts/VerdantWorld.cs`: map layout, terrain, rendering, fly camera, zone banner
- `Scripts/VerdantStructures.cs`: houses, town props, camps, ruins, bridges and where they're placed
- `Scripts/VerdantNature.cs`: trees, bushes, rocks, grass and flowers
- `Scripts/VTextures.cs`: paints the surface textures at startup
- `Scripts/MeshKit.cs`: noise and mesh-building helpers
- `Resources/*.shader`: toon, terrain, foliage, grass, water, sky and colour-grade shaders
- `Editor/VerdantSetup.cs`: the two menu items

## If something goes wrong
- **Everything is pink:** the project uses URP. Make a new project with the *Built-In Render Pipeline* template.
- **"Could not switch to WebGL":** install the WebGL Build Support module (see above).
- **Errors in the Console after importing:** send me the first error message and I'll fix it.
