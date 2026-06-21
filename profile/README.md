 # SwiftTUI

  **SwiftUI semantics, drawn in terminal cells.**

  ![Swift 6.3](https://img.shields.io/badge/Swift-6.3-F05138?logo=swift&logoColor=white)
  ![Platforms](https://img.shields.io/badge/platforms-macOS%20·%20Linux%20·%20iOS%20·%20WASI%20·%20Android-1E90FF)
  ![Status](https://img.shields.io/badge/prerelease-0.0.25-D06)
  ![License](https://img.shields.io/badge/license-MIT-3DA639)

  SwiftTUI is a SwiftUI-shaped UI framework — `View`, `Scene`, `App`, `@State`,
  `@FocusState`, `VStack`, `ProgressView`, custom `Layout` — that renders to
  terminal cells, a static browser bundle, a localhost WebHost, or an embedded
  SwiftUI surface. **One authored `App`. Four execution modes. The same view
  tree every time.**

  No `curses`. No virtual DOM. No global constraint solver.  
  Every frame is lowered through a strict, inspectable pipeline — `resolve → measure → place →
  semantics → draw → raster → commit` — so layout is deterministic and every
  frame is snapshot-testable.

  ## Project Index

  | What | Where |
  | --- | --- |
  | **Project Website, demos, documentation** | https://SwiftTUI.sh |
  | **DocC** | https://swifttui.sh/docs/documentation/ |
  | **Build a Terminal app with SwiftTUI** | [`SwiftTUI/swift-tui`](https://github.com/SwiftTUI/swift-tui) |
  | **Embed a SwiftTUI app in a website** | [`SwiftTUI/swift-tui-web`](https://github.com/SwiftTUI/swift-tui-web) |
  | **Embed a SwiftTUI app as a native SwiftUI view** (macOS · iOS) | [`SwiftTUI/swift-tui-swiftui`](https://github.com/SwiftTUI/swift-tui-swiftui) |
  | **Embed a SwiftTUI app with Android Compose** | [`SwiftTUI/swift-tui-android`](https://github.com/SwiftTUI/swift-tui-android) |
  | **Examples** full apps for each platform + explored use cases | [`SwiftTUI/swift-tui-examples`](https://github.com/SwiftTUI/swift-tui-examples) |

  ## Why SwiftTUI

  - **An excellent UI API** Stacks, frames, `@State`, `@Binding`, `@Environment`, view modifiers, gestures, and animations — that behave the way they should.
  - **Deterministic, testable frames.** Rendering is a pure function of the view
    tree and a size proposal. Same input, same cells, every time.
  - **Accessible by construction.** A semantic substrate sits under every frame,
    driving a linear accessibility path, `--no-color` / `--ascii` fallbacks, and
    reduce-motion behavior.
  - **Portable.** Beyond the terminal — Embed SwiftTUI apps using native drawing host libraries — not TTYs passing characters to a terminal emulator — for Web, Android, macOS and iOS.
  - **Batteries included.** The default `SwiftTUI` import wraps argument
    parsing, terminal launch, localhost WebHost launch, and animated GIF/image
    playback in one product.
