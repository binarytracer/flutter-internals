# Flutter Internals

[![CI](https://github.com/binarytracer/flutter-internals/actions/workflows/ci.yml/badge.svg)](https://github.com/binarytracer/flutter-internals/actions/workflows/ci.yml)
[![Security](https://github.com/binarytracer/flutter-internals/actions/workflows/security.yml/badge.svg)](https://github.com/binarytracer/flutter-internals/actions/workflows/security.yml)

> Flutter feels like magic until you look under the hood. This repo is where I look.

A hands-on playground for understanding **how Flutter really works**, and how to
use that knowledge to build **faster apps**. Every topic is a small, runnable
experiment: read the code, run it, break it, measure it.

## Why this repo exists

Most Flutter tutorials teach *what* to write. Few explain *why* a widget
rebuilds, why a list janks, or what actually happens between `setState` and
pixels on screen. Knowing the machinery turns performance tuning from guesswork
into engineering.

## What you'll find here

### Understanding the internals

- **The three trees**: Widget, Element and RenderObject, and how they cooperate
- **The build pipeline**: `setState` → dirty elements → build → layout → paint → composite
- **Keys and element reuse**: why keys matter and what happens without them
- **Constraints and layout**: "constraints go down, sizes go up, parent sets position"
- **Rendering**: layers, repaint boundaries, and the raster thread
- **The frame lifecycle**: vsync, the scheduler, and the 16 ms budget

### Optimization

- Cutting unnecessary rebuilds (`const`, widget splitting, scoped state)
- Taming expensive layouts and deep widget trees
- Efficient lists and scrolling (lazy building, `itemExtent`, caching)
- Avoiding `saveLayer` and other costly paint operations
- Finding bottlenecks with DevTools: Performance view, Widget Inspector, Timeline

## How to use it

```bash
git clone git@github.com:binarytracer/flutter-internals.git
cd flutter-internals
flutter pub get
flutter run
```

Suggested workflow for each experiment:

1. **Read** the code and predict what will happen.
2. **Run** it and check your prediction.
3. **Profile** it in [Flutter DevTools](https://docs.flutter.dev/tools/devtools) (use `flutter run --profile` on a real device for honest numbers).
4. **Change one thing** and measure again.

> Always measure in **profile mode**. Debug-mode performance is not representative.

## Quality

Every push and pull request runs formatting, static analysis and tests, plus a
dependency vulnerability scan. See [.github/workflows](.github/workflows).

```bash
dart format .
flutter analyze
flutter test
```

## Further reading

- [Flutter architectural overview](https://docs.flutter.dev/resources/architectural-overview)
- [Inside Flutter](https://docs.flutter.dev/resources/inside-flutter)
- [Flutter performance best practices](https://docs.flutter.dev/perf/best-practices)
- [Flutter source code](https://github.com/flutter/flutter), the best documentation there is

## Contributing

Spotted a mistake or have an experiment worth adding? Issues and PRs are
welcome. Internals are subtle and I'm learning too.
