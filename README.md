# Astronomy textures

Collection of textures useful for rendering astronomy scenes.

## Credit

See the [LICENSE](LICENSE.md) file and the readme file in each folder

## Use from Zig

A zig module containing lossily compressed versions of the textures is provided to easily embed them in executables.

Add the dependency in your `build.zig.zon` by running the following command:
```shell
zig fetch --save git+https://github.com/agagniere/astronomy_textures#master
```

Then, in your `build.zig`:
```zig
const astrotex = b.dependency("astronomy_textures", .{});

module.addImport("astronomy_textures", astrotex.module("assets"));
```

Example usage with raylib:
```zig
const astrotex = @import("astronomy_textures");

const skyboxImage = try raylib.loadImageFromMemory(".jpg", astrotex.skybox.stars);
// Apply rotations if necessary
const skyboxTexture = try skyboxImage.toTexture();
```
