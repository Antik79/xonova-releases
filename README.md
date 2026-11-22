<p align="center">
  <img src="assets/xonova-logo.png" alt="XONOVA" width="480">
</p>

<p align="center">
  <b>A free polyphonic wavetable synthesizer by MBSS (Monkey Business Soundsystem)</b><br>
  VST3 · CLAP · LV2 · Standalone &nbsp;|&nbsp; Linux x86_64 · Windows x64
</p>

<p align="center">
  <a href="https://mbss.be"><b>Download</b></a> ·
  <a href="docs/USER_GUIDE.md">User guide</a> ·
  <a href="docs/INSTALLING.md">Installing</a> ·
  <a href="docs/WAVETABLES.md">Wavetables</a> ·
  <a href="docs/FAQ.md">FAQ</a> ·
  <a href="https://github.com/Antik79/xonova-releases/releases">Release notes</a>
</p>

---

XONOVA is a hands-on wavetable synth for basses, leads, pads and everything in between. You build sounds
by dragging modulation straight onto knobs and watching the displays react as you play.

> **About this repository:** it holds release notes, version tags and the user documentation. It contains
> no source code. The plugin checks this repository to tell you when a new version is out.
> **Download XONOVA from the [Monkey Business Soundsystem website](https://mbss.be).**

## Features

**Sound sources**
- Three wavetable oscillators, each with two warp stages in series: phase bend, asymmetry, hard sync,
  spectral tilt and formant shift
- 40 factory wavetables, plus import of your own WAV wavetables
- Up to 8-voice unison per voice, with detune curve, stereo spread and position spread
- A modulation oscillator for ring, phase (FM-style) and audio-rate position modulation, and filter FM
- Noise source: white, pink, filtered and crackle

**Filters and routing**
- Two filters with 12 types: ladder and SVF low-pass, band-pass, high-pass, notch, combs, formant,
  Scream BP and allpass, each with up to 4x oversampling
- Serial/parallel blend between the filters, plus a feedback path
- A live **Routing** page that shows the whole signal flow and lights up with the signal

**Effects**
- Two per-voice inserts: bitcrusher, waveshaper, frequency shifter, sine shaper, delay comb, EQ band
- An eight-slot FX rack, in any order: chorus, flanger, phaser, tempo-synced delay, reverb, saturator,
  widener
- Output section with a three-band EQ and a safety limiter

**Modulation**
- Drag-and-drop modulation onto any knob
- Four envelopes with loops and custom curves
- Four LFOs with nine shapes, tempo sync, per voice or global
- Two step sequencers (up to 32 steps) and eight nameable macros
- A 64-slot modulation matrix with curves and scale sources
- Expressive MIDI sources: velocity, aftertouch, poly pressure, pitch bend and timbre (CC 74)

**Workflow**
- 200 factory presets in seven categories, with a browser that has search, tags, favourites and random
  audition
- MIDI learn for hardware controllers
- Full undo/redo
- Resizable interface (60–200 %)
- A playable on-screen and typing keyboard
- Poly, Mono and Legato modes with glide

## System requirements

| | Linux | Windows |
|---|---|---|
| **OS** | 64-bit, glibc 2.35 or newer (Ubuntu 22.04+, Debian 12+, Fedora 36+, Linux Mint 21+, current Arch / Manjaro / CachyOS) | 64-bit Windows |
| **Formats** | VST3, CLAP, LV2, Standalone | VST3, CLAP, Standalone |
| **Audio** | ALSA or JACK (PipeWire works through either) | Your DAW's audio setup |

macOS: there is no macOS release yet.

## Quick install

**Linux:** unpack the archive and run `./install.sh`, then rescan plugins in your DAW.

**Windows:** copy `XONOVA.vst3` to `C:\Program Files\Common Files\VST3` and `XONOVA.clap` to
`C:\Program Files\Common Files\CLAP`, then rescan plugins in your DAW.

Full instructions, including uninstalling and where your files live, are in [docs/INSTALLING.md](docs/INSTALLING.md).

## Documentation

| Document | What's in it |
|---|---|
| [User guide](docs/USER_GUIDE.md) | Everything from the window layout to modulation, presets and MIDI learn |
| [Installing](docs/INSTALLING.md) | Per-platform install, uninstall, requirements and file locations |
| [Wavetables](docs/WAVETABLES.md) | All 40 factory wavetables and how to import your own |
| [FAQ and troubleshooting](docs/FAQ.md) | Common questions, fixes, and how to report a problem |

## Updates

XONOVA checks this repository's [releases](https://github.com/Antik79/xonova-releases/releases) and shows
a badge in the plugin when a newer version is out. The badge links to the release notes; the download
itself is always on the [MBSS website](https://mbss.be). Beta versions are only offered to people running
a beta build.

## Reporting a problem

Open the **About** panel on the **Global** page and click **Copy system info**. Paste that into your
report together with what you played, which DAW you used and what went wrong. Screenshots and short
recordings help a lot. See [docs/FAQ.md](docs/FAQ.md#reporting-a-problem) for details.

## Licence

XONOVA is **free to use, but not open source**. You can use it on as many computers as you like, for
personal and commercial work, and everything you make with it is yours. You may not sell it, redistribute
it outside the MBSS website, or modify it. See [LICENSE.md](LICENSE.md) for the full terms. The download
includes the third-party notices.

---

<p align="center">
  Made by <a href="https://mbss.be"><b>MBSS · Monkey Business Soundsystem</b></a>
</p>
