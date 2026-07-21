# Synthatlas

<p align="center">

Texture Atlas & Sprite Workflow Tool

</p>

<p align="center">

##  Download

👉 **[Latest Release](https://github.com/ibrahiimbas/Synthatlas/releases)**

</p>

[![Status](https://img.shields.io/badge/version-beta_0.3.5-cyan?style=flat)](https://github.com/ibrahiimbas/Synthatlas.)

**A modern texture atlas and sprite workflow tool for indie game developers.**

Synthatlas is a desktop application built with WPF (.NET 8) that helps game developers pack sprite images into optimized texture atlases, export animation sheets, and manage sprite assets — all within a clean, dark-themed interface.

> [!NOTE]
> 🚧 **Early Development** – Synthatlas is under active early development. Bugs and errors are expected. Contributions and constructive feedback are highly welcome to make this project better.

---

<p align="center">
 <img width="1919" height="1008" alt="Image" src="https://github.com/user-attachments/assets/4d63ea57-a7bf-45f6-8f00-5ee6e9d50985" />
</p>
<p align="center">
  <em>Main Layout of Synthatlas</em>
</p>

---

## Features

### Atlas Packing
- **Four packing algorithms**: MaxRects, Guillotine, Skyline, Shelf — switchable on the fly
- **Auto-size mode**: calculates the smallest atlas that fits all sprites
- **Fixed size presets**: 256 / 512 / 1024 / 2048 / 4096 px
- **Power of Two** constraint (optional, auto-size mode only)
- **Configurable padding** between sprites (0–256 px)
- **Atlas trim**: canvas is cropped to the actual used area after packing

### Packing Algorithms

| Algorithm | Efficiency | Speed | Best For |
|---|---|---|---|
| **MaxRects** | 🔶🔶🔶🔶🔶 | 🔶🔶 | General use, large sprite sets |
| **Guillotine** | 🔶🔶🔶🔶 | 🔶🔶🔶🔶 | Balanced speed and efficiency |
| **Skyline** | 🔶🔶🔶🔶 | 🔶🔶🔶 | UI elements, uniform-height sprites |
| **Shelf** | 🔶🔶 | 🔶🔶🔶🔶🔶 | Quick tests, uniform sprites |

### Sprite Management
- **Import** via dialog or drag & drop (single files, multiple files, or entire folders)
- **Asset browser** with live search, sprite thumbnails, and size info
- **Right-click context menu**: remove sprite, clear all
- **File watcher**: auto-reloads sprites when source files change on disk
- **Duplicate detection** via SHA-256 hash

### Canvas & Viewport
- **Zoom** in/out with toolbar buttons or `Ctrl+Scroll` (mouse-centered)
- **Fit to screen** with `F` key
- **Pan** with middle mouse button or `Ctrl+drag`
- **Grid overlay** with configurable cell size (8 / 16 / 32 / 64 / 128 px) — GPU-accelerated via `DrawingBrush + TileMode.Tile`
- **Sprite outlines** and click-to-select with inspector highlight

### Animation Support
- **Automatic animation group detection** by naming pattern (`player_idle_01`, `player_idle_02`, …)
- **Animation preview window** with smooth playback, FPS control, and loop toggle
- **Single animation sheet export**: grid-based packing that preserves frame order with uniform padding
- **Multi-animation sheet export**: multiple animation groups packed onto a single sheet, each with individual column/padding settings
- Both sheet formats export `PNG/JPG + JSON/XML` metadata

<div align ="center>
<p align="center">
<img width="356" height="438" alt="Image" src="https://github.com/user-attachments/assets/76ce1bec-b7c2-4c50-84e7-be5b63add17a" />
   <img width="352" height="426" alt="Image" src="https://github.com/user-attachments/assets/9db33f86-7f06-4cdf-9c08-9579e34f817d" />
</p>
<p align="center">
  <em>Animation Preview Window</em>
</p>
</div>

### Export
- **Image formats**: PNG (with transparency) or JPG (with quality slider)
- **Metadata formats**: JSON or XML (TexturePacker / LibGDX compatible)
- **Export formats**:
  - `TextureAtlas` — standard sprite atlas
  - `AnimationSheet` — single animation grid
  - `MultiAnimationSheet` — multiple animations on one sheet
- Last used export folder is remembered across sessions

<div align ="center>
  
  <p align="center">
    <img width="490" height="596" alt="Image" src="https://github.com/user-attachments/assets/c0849b65-d566-478c-9752-dd30777279b8" />
    <img width="456" height="710" alt="Image" src="https://github.com/user-attachments/assets/2ff8b6f0-7318-47b7-990a-0ef4697d71a8" />
    <img width="459" height="713" alt="Image" src="https://github.com/user-attachments/assets/f5a92956-72d4-4fce-b9c9-8d9a0e0d8d2a" />
</p>
<p align="center">
  <em>Texture Atlas Export Windows</em>
</p>
</div>

### Workspace
- **Save / Load** workspaces (`.shat` format) — stores all sprite paths and settings
- **Recent projects** list (last 8)
- **Auto-save** with configurable interval
- **Unsaved changes indicator** (`*`) in the title bar — snapshot-based comparison

### Undo / Redo
- **Ctrl+Z / Ctrl+Y** for sprite additions, removals, and all settings changes
- In-memory bitmap cache — no disk I/O on undo, instant restore
- Up to 50 undo steps

### Other
- **Atlas Analyzer**: efficiency stats, duplicate detection, oversized sprite warnings
- **Console log**: color-coded entries with clear button
- **Toast notifications**: non-blocking export feedback
- **About / Help dialog**: keyboard shortcut reference
- **Feedback button**: direct link to bug report form
- **Themes:** Dark and Light theme.

<div align="center">
   <p align="center">
<img width="449" height="475" alt="Image" src="https://github.com/user-attachments/assets/095a1cf4-e08f-44f6-8887-a005b68ea621" />
</p>
<p align="center">
  <em>Texture Atlas Analyzer</em>
</p>
</div>

---

## Keyboard Shortcuts

| Key | Action |
|---|---|
| `Ctrl+N` | New workspace |
| `Ctrl+O` | Open workspace |
| `Ctrl+S` | Save workspace |
| `Ctrl+I` | Import sprites |
| `Ctrl+E` | Export atlas |
| `Ctrl+R` | Repack atlas |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `F` | Fit atlas to screen |
| `Ctrl+Scroll` | Zoom in / out |
| `Middle Mouse` | Pan canvas |
| `Ctrl+Drag` | Pan canvas |
| `Delete` | Remove selected sprite |
| `Escape` | Deselect sprite |
| `F1` | About / Shortcuts |

---

## Getting Started

### Requirements

- Windows 10 / 11

- 64-bit

- .NET Runtime not required (self-contained)

### Build & Run

- Download the latest ZIP from Releases.

- Extract the ZIP to any folder.

- Run Synthatlas.exe.

- No installation required.

---

## Unity Integration

Synthatlas exports XML in **TexturePacker / LibGDX format**, which can be used in Unity.

### SynthatlasPacker Editor Script

For full control and support for all three Synthatlas XML formats (`TextureAtlas`, `AnimationSheet`, `MultiAnimationSheet`), use the included editor script.

#### Installation

- **[SynthatlasPacker.cs](https://github.com/ibrahiimbas/Synthatlas/blob/main/unity-integration/SynthatlasPacker.cs)**

1. In your Unity project, create an `Assets/Editor/` folder if it doesn't exist
2. Copy `unity-integration/SynthatlasPacker.cs` into `Assets/Editor/`
3. Unity will compile it automatically — no setup required

#### Usage

1. In Synthatlas, export your atlas or animation sheet as XML
2. In Unity, open the menu: **Tools → Import Synthatlas Atlas or Sheet**
3. Select the `.xml` file exported from Synthatlas
4. If the image file is in the same folder as the XML, it will be found automatically. Otherwise Unity will ask you to select it manually
5. All sprites are sliced and imported with correct coordinates — done

#### Supported XML Formats

| Format | Root Element | Use Case |
|---|---|---|
| Texture Atlas | `<TextureAtlas>` | General sprite atlas |
| Animation Sheet | `<AnimationSheet>` | Single animation |
| Multi Animation Sheet | `<MultiAnimationSheet>` | Multiple animations on one sheet |

> [!NOTE]
> By default, sprites are imported with a center pivot `(0.5, 0.5)`. For character animations where sprites change size between frames (e.g. standing vs crouching), a bottom-center pivot `(0.5, 0)` prevents unwanted stretching. You can change this manually in Unity's Sprite Editor, or modify the `MakeSprite` method in the script to use `new Vector2(0.5f, 0f)`.

---

## Export Metadata Formats

### TextureAtlas XML

```xml
<TextureAtlas imagePath="atlas.png" width="512" height="256">
  <SubTexture name="player_idle_01" x="2"  y="2"  width="64" height="64"/>
  <SubTexture name="player_idle_02" x="68" y="2"  width="64" height="64"/>
</TextureAtlas>
```

### AnimationSheet XML

```xml
<AnimationSheet width="512" height="256" cols="4" rows="2" cellW="128" cellH="128" padding="2">
  <Frame index="0" name="run_01" x="2"   y="2"   w="124" h="124"/>
  <Frame index="1" name="run_02" x="130" y="2"   w="124" h="124"/>
</AnimationSheet>
```

### MultiAnimationSheet XML

```xml
<MultiAnimationSheet width="512" height="600" animationCount="2">
  <Animation name="idle" frameCount="4" cols="4" rows="1" cellW="128" cellH="128" padding="2" offsetY="0">
    <Frame index="0" name="idle01" x="2" y="2" w="124" h="124"/>
  </Animation>
  <Animation name="run" frameCount="4" cols="4" rows="1" cellW="128" cellH="128" padding="2" offsetY="132">
    <Frame index="0" name="run01" x="2" y="134" w="124" h="124"/>
  </Animation>
</MultiAnimationSheet>
```

### TextureAtlas JSON*

```json
{
  "meta": {
    "app": "Synthatlas",
    "version": "0.3.5",
    "image": "full_atlas.png",
    "format": "RGBA8888",
    "size": {
      "w": 260,
      "h": 260
    },
    "scale": "1"
  },
  "frames": [
    {
      "filename": "UI_Icons_Button",
      "frame": {
        "x": 2,
        "y": 2,
        "w": 256,
        "h": 256
      },
      "rotated": false,
      "trimmed": false,
      "spriteSourceSize": {
        "x": 0,
        "y": 0,
        "w": 256,
        "h": 256
      },
      "sourceSize": {
        "w": 256,
        "h": 256
      },
      "pivot": {
        "x": 0.5,
        "y": 0.5
      }
    }
  ]
}
```

---

## Workspace File Format

Workspaces are saved as `.shat` JSON files:

```json
{
  "name": "my_game_sprites",
  "spritePaths": [
    "C:/art/player_idle_01.png",
    "C:/art/player_idle_02.png"
  ],
  "settings": {
    "padding": 2,
    "sizeOption": "Auto",
    "powerOfTwo": true,
    "algorithm": 0,
    "autoSave": true,
    "autoSaveInterval": 5,
    "autoReload": false
  }
}
```

---

## Built With

- [.NET 8](https://dotnet.microsoft.com/) + WPF
- C# 12
- [CommunityToolkit.Mvvm](https://github.com/CommunityToolkit/dotnet)
- MVVM architecture
- GPU-accelerated grid overlay via `DrawingBrush + TileMode.Tile`
- Snapshot-based undo/redo with in-memory bitmap cache

---

## License

- Synthatlas is free to use.

- The source code is not publicly available.

---

## Credit

- Built by [**ibrahiimbas**](https://github.com/ibrahiimbas) (Synthesizer).
- Sprites on the screenshots from [Momento Pole](https://store.steampowered.com/app/3618900/Momento_Pole/), drawn by [theWisteriaa](https://github.com/theWisteriaa)

