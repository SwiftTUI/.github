# SwiftTUI

**Views, State, Observation, Gestures, and Animations: SwiftUI semantics, drawn in terminal cells.**

![Swift 6.3](https://img.shields.io/badge/Swift-6.3-F05138?logo=swift&logoColor=white)
![Status](https://img.shields.io/badge/beta-0.9.7-DAA520)
![License](https://img.shields.io/badge/license-MIT-3DA639)

TUI toolkits make you choose between a low-level draw loop and a widget set
with its own novel state story. SwiftTUI instead takes the declarative model
SwiftUI has proven — interface is a function of state — and aims it at terminal
cells. You declare views; the framework owns layout, focus, redraw, and the
terminal itself. The result is one fast native binary for macOS, Linux, and
Windows.

[<img width="545" height="321" alt="counter-demo" src="https://github.com/user-attachments/assets/15cd2cb5-e907-4456-b699-2906dc3682b1" />](https://swifttui.sh/webexample/)

A real SwiftTUI app, compiled to WebAssembly and
[running live in your browser](https://swifttui.sh/webexample/).

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
  cells that changed. No draw loop, no buffer diffing, no repaint bookkeeping.
- **The terminal, negotiated for you.** Truecolor, Kitty and Sixel images,
  OSC 8 hyperlinks, and mouse reporting are probed per session and degrade
  gracefully: one binary is correct in kitty, a bare SSH session, or CI. Every
  app also ships `--accessible`, `--cursor-follows-focus`, `--reduce-motion`,
  `--no-color`, and `--ascii`. You write views, not escape codes.
- **One compiled binary, testable without a TTY.** Swift 6 compiles your
  interface into a single executable with checked concurrency, and tests
  render and compare integer-cell frames with no terminal attached.

**Terminal first, not terminal only.** The same authored `App` also runs in the
browser, in native macOS and iOS windows, and on Android (arm64 preview) —
natively, not through a terminal emulator.

Under the hood, every frame is lowered through a strict, inspectable render
pipeline — the walkthrough is at
[swifttui.sh/pipeline](https://swifttui.sh/pipeline/).

## Build with us

Development happens on GitHub and [Discord](https://discord.gg/8j35kYDFxn).
Come ask questions, show what you are building, or talk through a contribution.
