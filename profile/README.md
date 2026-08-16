# SwiftTUI

**Views, State, Observation, Gestures, and Animations: SwiftUI semantics, drawn in terminal cells.**

![Swift 6.3](https://img.shields.io/badge/Swift-6.3-F05138?logo=swift&logoColor=white)
![Platforms](https://img.shields.io/badge/platforms-macOS%20·%20Linux%20·%20iOS%20·%20WASI%20·%20Android-1E90FF)
![Status](https://img.shields.io/badge/beta-0.9.1-DAA520)

TUI toolkits make you choose between a low-level draw loop and a widget
set with its own novel state story.  
SwiftTUI instead take the declarative model SwiftUI has proven — that interface is a function of
state — and aims it at terminal cells. You declare views; the framework owns
layout, focus, redraw, and the terminal itself.

Under the hood, every frame is lowered through a strict, inspectable pipeline
(`resolve → measure → place → semantics → draw → raster → commit`), with no
global solver, virtual DOM, or `curses`. Layout is deterministic and every
frame is snapshot-testable.

**Terminal first, not terminal only.** When you need it, the same authored
`App` (same view tree, same `@State`, same `@FocusState`, etc.) compiles for
the browser as a static WASI bundle, for native macOS and iOS windows, and for Android.  
Hosts display and run the app natively — not through an emulated TTY. No `xterm.js`, no `libghostty`, etc.

## Project index

| What | Where |
| --- | --- |
| **Primary repo**: build a terminal app | [`SwiftTUI/swift-tui`](https://github.com/SwiftTUI/swift-tui) |
| **Run the web demo, read the intro** | <https://swifttui.sh> |
| **Quick-start**: the Counter App demo | [`SwiftTUI/swift-tui-counter-demo`](https://github.com/SwiftTUI/swift-tui-counter-demo) |
| &nbsp; | &nbsp; |
| **Read the documentation** | <https://swifttui.sh/docs/documentation/> |
| **Examples**: demo apps across all host platforms | [`SwiftTUI/swift-tui-examples`](https://github.com/SwiftTUI/swift-tui-examples) |
| **Embed in a website** | [`SwiftTUI/swift-tui-web`](https://github.com/SwiftTUI/swift-tui-web) |
| **Embed in SwiftUI** (macOS · iOS) | [`SwiftTUI/swift-tui-swiftui`](https://github.com/SwiftTUI/swift-tui-swiftui) |
| **Embed in Android** | [`SwiftTUI/swift-tui-android`](https://github.com/SwiftTUI/swift-tui-android) |
| **Add charts & dashboards** | [`SwiftTUI/swift-tui-charts`](https://github.com/SwiftTUI/swift-tui-charts) |

## Why SwiftTUI

- **State in, screen out.** Views are a pure function of your app's state:
  change a value and the runtime recomputes layout and rewrites exactly the
  cells that changed.
- **Useful components, focus based navigation.** Buttons, text fields, pickers, sliders,
  scroll views, and charts, with a focus engine, tab traversal, keyboard
  chords. You compose behavior instead of hand-routing key events to widgets.
- **Make the terminal dance** Advanced functionality is ported from SwiftUI. Tap · drag · hover gestures,
  animations and transitions, images, and even mesh gradients, all behave like in SwiftUI.
- **The terminal, negotiated for you.** Truecolor, Kitty and Sixel images,
  OSC 8 hyperlinks, and mouse reporting are probed per session and degrade
  gracefully; one binary is correct in kitty, a bare SSH session, or CI. You
  write views, not escape codes.
- **Developer ergonomics** Your app compiles into a single fast executable with checked
  concurrency. Layout and state are type-checked at build time, and tests render frames
  as integer-cell rasters without a TTY.
- **Batteries included, accessible by default.** Default builds provide accessibility
  flags `--reduced-motion`, `--cursor-follows-focus`, and even `--web` for a browser view.
  Terminal conveniences like `--no-color`, and `--ascii` are similarly bundled.

## Build with us

Development happens on GitHub and [Discord](https://discord.gg/8j35kYDFxn).
Come ask questions, show what you are building, or talk through a contribution.
