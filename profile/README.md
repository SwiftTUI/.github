 # SwiftTUI

  **SwiftUI semantics, drawn in terminal cells.**

  ![Swift 6.3](https://img.shields.io/badge/Swift-6.3-F05138?logo=swift&logoColor=white)
  ![Platforms](https://img.shields.io/badge/platforms-macOS%20%C2%B7%20Linux%20%C2%B7%20iOS%20%C2%B7%20WASI-1E90FF)
  ![Status](https://img.shields.io/badge/status-0.0.4%20alpha-DAA520)
  ![License](https://img.shields.io/badge/license-MIT-3DA639)

  SwiftTUI is a SwiftUI-shaped UI framework — `View`, `Scene`, `App`, `@State`,
  `@FocusState`, `VStack`, `ProgressView`, custom `Layout` — that renders to
  terminal cells, a static browser bundle, a localhost WebHost, or an embedded
  SwiftUI surface. **One authored `App`. Four execution modes. The same view
  tree every time.**

  No `curses`. No virtual DOM. No global constraint solver. Every frame is
  lowered through a strict, inspectable pipeline — resolve → measure → place →
  semantics → draw → raster → commit — so layout is deterministic and every
  frame is snapshot-testable.

  ## Pick your entry point

  | If you want to… | Go to |
  | --- | --- |
  | **Use SwiftTUI** in your Swift package | [`SwiftTUI/swift-tui`](https://github.com/SwiftTUI/swift-tui) — the SwiftPM framework |
  | **Embed terminal output** in a browser or Node app | [`SwiftTUI/swift-tui-web`](https://github.com/SwiftTUI/swift-tui-web) |
  | **Embed a SwiftTUI app in a native SwiftUI view** (macOS · iOS) | [`SwiftTUI/swift-tui-swiftui`](https://github.com/SwiftTUI/swift-tui-swiftui) |
  | **Read code that runs** — full apps, snapshot tests, the gallery | [`SwiftTUI/swift-tui-examples`](https://github.com/SwiftTUI/swift-tui-examples) |
  | **Project Website, demos, documentation** | https://SwiftTUI.sh |
  | **DocC** | https://swifttui.sh/docs/documentation/ |

  ## Why SwiftTUI

  - **You already know the API.** Stacks, frames, `@State`, `@Environment`,
    `ProgressView`, `LabeledContent`, gestures, view modifiers — they behave the way
    SwiftUI taught you to expect.
  - **Deterministic, testable frames.** Rendering is a pure function of the view
    tree and a size proposal. Same input, same cells, every time.
  - **Accessible by construction.** A semantic substrate sits under every frame,
    driving a linear accessibility path, `--no-color` / `--ascii` fallbacks, and
    reduce-motion behavior.
  - **Portable.** Terminal, browser, and embedded host are sibling products of
    one package — not three rewrites.
  - **Batteries included.** The default `SwiftTUI` import wraps argument
    parsing, terminal launch, localhost WebHost launch, and animated GIF/image
    playback in one product.
