<p align="center">
  <img src="../assets/xonova-logo.png" alt="XONOVA" width="360">
</p>

# User guide

XONOVA is a polyphonic wavetable synthesizer: three wavetable oscillators with two warp stages each,
a modulation oscillator, noise, two filters that run in series or parallel, two per-voice inserts, an
eight-slot effects rack, and a modulation system you mostly use by dragging.

- [Installing](#installing)
- [The window](#the-window)
- [Playing it](#playing-it)
- [Sound sources](#sound-sources)
- [Filters and the signal flow](#filters-and-the-signal-flow)
- [Inserts and effects](#inserts-and-effects)
- [Modulation](#modulation)
- [Presets](#presets)
- [Hardware controllers (MIDI learn)](#hardware-controllers-midi-learn)
- [Undo, settings and files](#undo-settings-and-files)
- [Keyboard shortcuts](#keyboard-shortcuts)

## Installing

See [INSTALLING.md](INSTALLING.md) for per-platform instructions, requirements and uninstalling. Short
version: on Linux run `./install.sh` from the unpacked archive; on Windows copy `XONOVA.vst3` and
`XONOVA.clap` to the Common Files plugin folders. Then rescan plugins in your DAW.

## The window

The header holds, from left to right:

- the page tabs: **Synth**, **Routing**, **FX**, **Matrix** and **Global**
- undo and redo
- the preset bar (click the name for the browser, the arrows step through presets)
- the polyphony (drag up or down)
- the output level and meter (the dot lights when the safety limiter works)
- the number of sounding voices, the CPU load and the gear menu

The CPU figure is the share of each audio block's real time this instance needs; near 100 % you get
dropouts.

The footer is a playable keyboard with pitch and mod wheels. The window can be resized (gear menu,
**Interface size**, from 60 % to 200 %, or drag the corner); everything scales. A new instance opens at the
size you last chose, never larger than your screen.

Everything you can turn has a tooltip. Double-click a control to reset it, hold Ctrl (Cmd on macOS)
while dragging for fine steps, and use the mouse wheel. To type a value, **middle-click** a knob, slider or
value field (or right-click a knob or slider and choose **Enter value...**): units are optional ("2k" or "2 kHz", "1.5 s", "80 %"). Clicked controls take
keyboard focus: the arrow keys step them.

### Live feedback

While notes play, the displays show what the sound is doing, not just the settings:

- **Wavetables:** the bright frame is the one the newest note plays, including modulation; dots mark
  other notes on other frames.
- **Envelopes and LFOs:** a playhead runs along the shape.
- **Step sequencers:** the playing step is lit.
- **Filters:** the response is drawn at the modulated cutoff.
- **Modulated knobs:** a bright dot shows where the value really is.
- **Section titles:** a light next to each title shows signal passing through.

**Animated displays** in the gear menu turns all of this off.

## Playing it

- **Keyboard:** click or drag on the footer keys (lower on a key is louder). With the window focused you
  can play with the computer keyboard: the A row (A S D F G H J K L) for white keys, W E T Y U O P for
  black keys, Z and X to move the octave. A blue strip shows which keys the typing keys reach. Your
  DAW may keep some keys for itself; the standalone app gets them all.
- **Wheels:** the pitch wheel springs back; the mod wheel stays where you leave it. Both behave like a
  hardware controller's wheels.
- **Voices:** the polyphony sets how many notes play at once. Lower it while notes sound and the oldest
  fade out. Play modes (Global page): Poly, Mono and Legato, with glide.

## Sound sources

### Wavetable oscillators (Osc 1-3)

Each oscillator plays a **wavetable**: a series of single-cycle frames. **Position** moves through them.
Click the table name to choose one of the 40 factory tables (see [WAVETABLES.md](WAVETABLES.md)) or import
a WAV file; the arrows step through the tables.

- **Warp 1 and Warp 2** reshape the wave in series. Click a warp's label to choose its mode:
  - Phase Bend +, -, +/-
  - Asymmetry
  - Hard Sync
  - Spectral Tilt
  - Formant Shift
- **Pitch:** Oct, Semi and Fine set the pitch. Phase and Start (Free, Fixed, Random) set where each
  note's wave begins.
- **Level** sets the volume and **Pan** the stereo position.
- **Filter** balances the oscillator between Filter 1 and Filter 2.
- **Unison** (Global page) stacks up to 8 detuned copies of each voice, with detune curve, stereo spread
  and position spread.

### Mod oscillator

A simple oscillator (sine, triangle, saw, square) that modulates the others. Its pitch follows the key (a
ratio) or stays fixed. Per oscillator it can **Ring** modulate, **Phase** modulate (FM-style tones),
or move the table **Position** at audio rate. It can also modulate both filters' cutoff.

### Noise

White, pink, filtered and crackle noise with a colour control, routed to the filters like an oscillator.

## Filters and the signal flow

Two filters with 12 types:

- low-pass: Ladder LP 24, SVF LP 12, LP 6
- other SVF modes: SVF BP 12, SVF HP 12, SVF Notch 12
- high-pass: HP 6
- combs: Comb + and Comb -
- character types: Formant, Scream BP and Allpass

Each filter has cutoff, resonance, a type-dependent **Character**, key tracking, drive and level, and runs
at 1x, 2x or 4x oversampling (more is cleaner and costs more CPU). With key tracking at 100 % the comb
filters ring at the note you play.

The **Routing** panel (and the **Routing** page) set the filter routing:

- **Serial/parallel** blends from Filter 1 into Filter 2 (serial) to both side by side (parallel).
- **Feedback** sends the output back into Filter 1's input, tapped after Filter 1 or after the mix.

The **Routing page** shows the whole signal flow as a diagram that lights up with the signal. Drag a
source's F1/F2 handle, the serial/parallel and feedback handles, click power symbols, drag the inserts
onto their positions and drag FX slots to reorder the chain.

## Inserts and effects

**Inserts** are two per-voice effects, placed before or after Filter 1, before Filter 2 or after both:

- Bitcrusher
- Waveshaper
- Frequency Shifter
- Sine Shaper
- Delay Comb
- EQ Band

The **FX rack** has eight slots after the voices: chorus, flanger, phaser, delay (tempo synced), reverb,
saturator and widener. Any type can go in any slot. Change the order from a slot's menu or on the Routing
page. The **Output** section has a three-band EQ, the output level and a safety limiter.

## Modulation

Sources: four envelopes (Env 4 drives the amp), four LFOs, two step sequencers, eight macros, and
velocity, note, random, mod wheel, aftertouch, poly pressure, pitch bend and timbre (CC 74).

**To modulate something, drag a source onto a knob.** Drag a tab from the modulation panel (Env 1,
LFO 2, Seq 1 ...), a macro's handle or one of the chips under the macros (velocity, note, wheel and so
on). The knob gets a coloured ring showing the range.

- **Alt-drag** the knob to change the depth of its active routing.
- **Right-click** the knob to invert a routing, scale it by another source (a macro, the wheel ...), pick
  which routing Alt-drag adjusts, or remove routings.
- The **Matrix** page lists every routing with source, target, amount, curve and scale source, and
  adds routings by menu.

Envelopes: delay, attack, hold, decay, sustain, release, with curves, loops (sustain loop or free loop)
and velocity sensitivity. Drag the handles on the display. **Custom** shape mode draws your own curve.

LFOs: nine shapes (including sample & hold, smooth random, a wavetable morph and a drawn **Custom**
shape), free rate or tempo sync, retrigger, free or one-shot, fade-in, per voice or global.

Step sequencers: up to 32 steps, step length in note divisions, swing and glide. Draw the steps with the
mouse.

Macros: eight knobs you can name (double-click the label) and route anywhere; presets use them for the
most useful moves.

## Presets

Click the preset name in the header to open the **browser**:

- **Finding presets:** search by name, tag, category or author (Ctrl/Cmd+F jumps to the search). Filter
  by origin (all, favourites, factory, yours), category (with counts) and tags. Click **Name** or
  **Category** above the list to sort.
- **Auditioning:** click a preset or use the arrow keys. Enter or a double-click loads it and closes the
  browser; Escape clears the search, then closes. **Random** auditions a random preset from the list.
- **Managing presets:** the star marks a favourite. Right-click a preset to load, favourite, rename or
  delete it (your own presets), or show its file. **Save current sound...** stores your preset with a
  name, category, tags, author and a comment (shown in the browser and found by the search); **Init**
  starts from scratch.

XONOVA has 200 factory presets in seven categories (Bass, Lead, Pad, Pluck, Keys, FX, Sequence).

## Hardware controllers (MIDI learn)

Right-click a knob or slider and choose **MIDI learn**, then move a knob or fader on your controller. The
control is outlined until it receives one; Escape cancels. From then on that controller (CC) moves it on
any MIDI channel, and your DAW can record the moves as automation. Right-click again to forget it; the gear
menu's **MIDI controllers** lists every assignment.

Assignments are saved as your default and come with you into new sessions; a session saved with its own
assignments uses those. Presets never change them. Bank select, sustain and channel-mode messages can't be
assigned. CC 1 (mod wheel) and CC 74 (timbre) keep their built-in roles when assigned.

## Undo, settings and files

**Undo and redo** cover every edit, including routings, curves, steps, tables, FX order, a preset
load and hardware controller moves. One drag or one preset load is one step. Use the header arrows,
Ctrl/Cmd+Z and Ctrl/Cmd+Shift+Z (or Ctrl+Y).

The **gear menu**:

- the interface size
- animated displays
- MIDI controllers
- the presets and wavetables folders

Settings are global: they're not stored in presets or sessions.

**Reporting a problem:** the About panel on the Global page has **Copy system info**. Paste it into
your report: it lists the version, plugin format, host, system and audio settings. See
[FAQ.md](FAQ.md#reporting-a-problem).

Your files live in `~/.local/share/MBSS/XONOVA` on Linux and `%APPDATA%\MBSS\XONOVA` on Windows:

- `Presets/`
- `Wavetables/`
- `Favourites.txt`
- `Settings.xml`
- `MidiMappings.xml`

## Keyboard shortcuts

| Keys | Does |
|---|---|
| A S D F G H J K L ; / W E T Y U O P | Play notes (typing keyboard) |
| Z / X | Octave down / up |
| Ctrl/Cmd+Z | Undo |
| Ctrl/Cmd+Shift+Z, Ctrl+Y | Redo |
| Escape | Cancel MIDI learn; in the browser: clear the search, then close |
| Ctrl/Cmd+F | Browser: search |
| Arrow keys | Step the focused control; in the browser: audition presets |
| Enter | Browser: load and close |

---

[← Back to the README](../README.md) · [Installing](INSTALLING.md) · [Wavetables](WAVETABLES.md) · [FAQ](FAQ.md)
