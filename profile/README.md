# SwiftTUI

**Build Swift Terminal User Interfaces — Views, State, Observation, Gestures,
Animations: SwiftUI semantics, drawn in terminal cells.**

![Swift 6.3](https://img.shields.io/badge/Swift-6.3-F05138?logo=swift&logoColor=white)
![Platforms](https://img.shields.io/badge/platforms-macOS%20·%20Linux%20·%20iOS%20·%20WASI%20·%20Android-1E90FF)
![Status](https://img.shields.io/badge/pre--release-0.8.0-DAA520)

Most TUI toolkits make you choose between a low-level draw loop and a widget
set with its own ad-hoc state story. SwiftTUI instead borrows the declarative
model SwiftUI has proven at platform scale — the interface is a function of
state — and aims it at terminal cells. You declare views; the framework owns
layout, focus, redraw, and the terminal itself.

Under the hood, every frame is lowered through a strict, inspectable pipeline —
`resolve → measure → place → semantics → draw → raster → commit` — no global
solver, no virtual DOM, no `curses`. Layout is deterministic and every frame is
snapshot-testable.

**Terminal first, not terminal only.** When you need it, the same authored
`App` — the same view tree, the same `@State`, the same `@FocusState` — also
runs in the browser as a static WASI bundle or a localhost WebHost, in native
macOS and iOS windows, and on Android. Both browser paths render to the DOM
with a real accessibility tree, not a terminal emulator.

## Project Index

| What | Where |
| --- | --- |
| **Run the demo, read the docs** | <https://swifttui.sh> |
| **Read the DocC** | <https://swifttui.sh/docs/documentation/> |
| **Build a terminal app** | [`SwiftTUI/swift-tui`](https://github.com/SwiftTUI/swift-tui) |
| **Add charts & dashboards** | [`SwiftTUI/swift-tui-charts`](https://github.com/SwiftTUI/swift-tui-charts) — [charts DocC](https://swifttui.sh/docs/charts/documentation/swifttuicharts/) |
| **Embed in a website** | [`SwiftTUI/swift-tui-web`](https://github.com/SwiftTUI/swift-tui-web) |
| **Embed as a native SwiftUI view** (macOS · iOS) | [`SwiftTUI/swift-tui-swiftui`](https://github.com/SwiftTUI/swift-tui-swiftui) |
| **Embed in Android Compose** | [`SwiftTUI/swift-tui-android`](https://github.com/SwiftTUI/swift-tui-android) |
| **Examples** — full apps per host + explored use cases | [`SwiftTUI/swift-tui-examples`](https://github.com/SwiftTUI/swift-tui-examples) |
| **The website itself** — Astro + DocC build | [`SwiftTUI/swift-tui-site`](https://github.com/SwiftTUI/swift-tui-site) |

## Why SwiftTUI

- **State in, screen out.** No draw loop, no buffer diffing, no repaint
  bookkeeping. Views are a pure function of your app's state: change a value
  and the runtime recomputes layout and rewrites exactly the cells that
  changed.
- **Real components, real focus.** Buttons, text fields, pickers, sliders,
  scroll views, and charts, with a focus engine, tab traversal, keyboard
  chords, tap · drag · hover gestures, and animation built in. You compose
  behavior instead of hand-routing key events to widgets.
- **The terminal, negotiated for you.** Truecolor, Kitty and Sixel images,
  OSC 8 hyperlinks, and mouse reporting are probed per session and degrade
  gracefully — one binary is correct in kitty, a bare SSH session, or CI. You
  write views, never escape codes.
- **One compiled binary.** Swift 6 compiles your interface into a single fast
  executable with checked concurrency. Layout and state are type-checked at
  build time, and tests render frames as integer-cell rasters — no TTY
  required.

## Build with us

Development happens in public on GitHub, and the people building SwiftTUI are
on [Discord](https://discord.gg/8j35kYDFxn). Come ask questions, show what you
are building, or talk through a contribution.
