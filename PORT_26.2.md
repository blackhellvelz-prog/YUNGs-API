# YUNG's API 6.1.3 — unofficial port to Minecraft 26.2 (NeoForge 26.2.0.88)

This branch (`port-26.2-dum`) ports [YUNG's API](https://github.com/YUNG-GANG/YUNGs-API) by YUNGNICKYOUNG to
Minecraft 26.2 for the Misty Dale modpack (it is the library the 26.2 port of Ribbits needs). It is **not** an
official release and is not supported by the original author. When an official 26.2 version appears, use that one.

License: GNU LGPL v3 (unchanged, see `LICENSE`). Only the NeoForge side was ported.

## What changed (8 files)
- `StructureProcessor` is an interface in 26.2 and its registry holds `MapCodec`s: AutoRegister routes `MapCodec`
  fields into that registry; `StructureEntityProcessorBuilder.build()` returns a `MapCodec`.
- `EntityType.ARMOR_STAND/ITEM_FRAME` → `EntityTypes`; `immuneTo` takes a `TagKey<Block>`;
  `NeoForgeMod.NAMETAG_DISTANCE` → `Attributes.NAME_TAG_DISTANCE`; `BLACK_WALL_BANNER` → `WALL_BANNER.pick(BLACK)`.
- The jigsaw pool weight-limit mixin also targets `lambda$static$0`, where 26.2 keeps `Codec.intRange(1, 150)`
  (with `require = 0` it would otherwise silently not apply).

Built with plain `javac` against the 26.2 client (no Gradle update), Common + NeoForge sources merged.
