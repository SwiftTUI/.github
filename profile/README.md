# SwiftTUI

**SwiftUI semantics, drawn in terminal cells.**

![Swift 6.3](https://img.shields.io/badge/Swift-6.3-F05138?logo=swift&logoColor=white)
![Platforms](https://img.shields.io/badge/platforms-macOS%20·%20Linux%20·%20iOS%20·%20WASI%20·%20Android-1E90FF)
![Status](https://img.shields.io/badge/prerelease-0.0.27-D06)
![License](https://img.shields.io/badge/license-MIT-3DA639)

SwiftTUI is a SwiftUI-shaped UI framework — `View`, `Scene`, `App`, `@State`,
`@FocusState`, `VStack`, `ProgressView`, custom `Layout` — that renders to
terminal cells, a static WASI bundle, a localhost WebHost, a native SwiftUI
surface, or an Android Compose surface. **One authored `App`. Five hosts. The
same view tree, the same `@State`, the same `@FocusState` every time.**

Under the hood, every frame is lowered through a strict, inspectable pipeline —
`resolve → measure → place → semantics → draw → raster → commit` — no global
solver, no virtual DOM, no `curses`. Layout is deterministic and every frame is
snapshot-testable.

## Project Index

| What | Where |
| --- | --- |
| **Run the demo, read the docs** | https://SwiftTUI.sh |
| **Read the DocC** | https://swifttui.sh/docs/documentation/ |
| **Build a terminal app** | [`SwiftTUI/swift-tui`](https://github.com/SwiftTUI/swift-tui) |
| **Embed in a website** | [`SwiftTUI/swift-tui-web`](https://github.com/SwiftTUI/swift-tui-web) |
| **Embed as a native SwiftUI view** (macOS · iOS) | [`SwiftTUI/swift-tui-swiftui`](https://github.com/SwiftTUI/swift-tui-swiftui) |
| **Embed in Android Compose** | [`SwiftTUI/swift-tui-android`](https://github.com/SwiftTUI/swift-tui-android) |
| **Examples** — full apps per host + explored use cases | [`SwiftTUI/swift-tui-examples`](https://github.com/SwiftTUI/swift-tui-examples) |

## Why SwiftTUI

- **It's SwiftUI, so your SwiftUI knowledge transfers.** Stacks, frames,
  `@State`, `@Binding`, `@Environment`, view modifiers, gestures, and animations
  behave the way SwiftUI taught you to expect.
- **Deterministic, testable frames.** Rendering is a pure function of the view
  tree and a size proposal — same input, same cells, every time.
- **Accessible by construction.** A semantic substrate sits under every frame,
  driving a linear accessibility path, `--no-color` / `--ascii` fallbacks, and
  reduce-motion behavior.
- **Real native drawing on every host.** Web, Android, macOS, and iOS hosts draw
  through native drawing libraries — not a TTY shipping characters to a terminal
  emulator — so the same view tree looks right everywhere.
- **Batteries included.** The default `SwiftTUI` import wraps argument parsing,
  terminal launch, localhost WebHost launch, and animated GIF/image playback in
  one product.
