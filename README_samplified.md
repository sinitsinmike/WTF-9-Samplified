# 🎛 SAMPLIFIED (Arduino Drum Sequencer)

Step-based 4-voice drum sequencer / looper built on Arduino Nano.

------------------------------------------------------------------------

## 🔥 Features

-   4 drum voices (trigger-based)
-   32-step sequencer
-   4 pattern banks
-   Real-time recording
-   MIDI input support
-   Clock / tempo control
-   Reverse playback
-   Noise mode (alt synthesis engine)

------------------------------------------------------------------------

## 🧱 Hardware

-   Arduino Nano
-   MCP4901 DAC
-   8 buttons
-   2 potentiometers
-   3x Jack (audio / sync)
-   LED indicator

------------------------------------------------------------------------

## 🎛 Control Layout

            [ RED ]   [ BLUE ]
            [ GREEN ] [ YELLOW ]

       [ SHIFT ] [ TAP ]
       [ REC   ] [ PLAY ]

       POT1          POT2

------------------------------------------------------------------------

## 🎹 Sound Mapping

  Button      Voice   Description
  ----------- ------- --------------
  🔴 Red      B1      High / click
  🔵 Blue     B2      Bass / tom
  🟢 Green    B3      Snare / clap
  🟡 Yellow   B4      Kick

------------------------------------------------------------------------

## ▶️ Transport

  Button   Action
  -------- ------------------------------
  Play     Start / Stop
  Rec      Toggle recording (auto play)
  Tap      Tap tempo
  Shift    Modifier / hidden functions

------------------------------------------------------------------------

## 🥁 Live Play

Hold **SHIFT** and press buttons:

-   Red → B1\
-   Blue → B2\
-   Green → B3\
-   Yellow → B4

------------------------------------------------------------------------

## 🎙 Recording

1.  Press **REC**
2.  Playback starts automatically
3.  Hold **SHIFT**
4.  Play buttons in rhythm
5.  Press **REC** again to stop

👉 Recording is step-based, not audio.

------------------------------------------------------------------------

## 🧽 Clear Pattern

Hold **REC + PLAY**

------------------------------------------------------------------------

## 🧠 Pattern Structure

-   32 steps per pattern
-   4 banks
-   Looping playback

------------------------------------------------------------------------

## 🗂 Pattern Banks

(when SHIFT is NOT pressed)

  Button   Bank
  -------- --------
  Blue     Bank 1
  Yellow   Bank 2
  Red      Bank 3
  Green    Bank 4

------------------------------------------------------------------------

## 🎚 Knobs

### Normal Mode

  Knob   Function
  ------ ----------------------------
  Pot1   B1 parameter (pitch/speed)
  Pot2   B2 parameter

------------------------------------------------------------------------

### Noise Mode

Two pages:

  Mode     Knobs
  -------- ------------
  Page 1   Pot1, Pot2
  Page 2   Pot3, Pot4

------------------------------------------------------------------------

## ⚙️ Advanced Functions

### 🔁 Reverse Playback

Press **PLAY** (without SHIFT)

### 🔊 Metronome

Hold **SHIFT** (long)

### 🎚 Tempo from Knob

Press **TAP** (without SHIFT)

------------------------------------------------------------------------

## ⚡ Startup Modes

### Noise Mode

Hold **SHIFT while powering on**

### MIDI Channel Select

Hold button on startup:

  Button   Channel
  -------- ---------
  Red      1
  Green    2
  Blue     3
  Yellow   4
  None     Omni

------------------------------------------------------------------------

## 🎧 MIDI Mapping

### Notes

  Note          Action
  ------------- ------------
  60            B1
  62            B2
  64            B3
  65            B4
  67            Play
  69            Reverse
  70            Noise mode
  72/74/76/77   Banks

------------------------------------------------------------------------

### CC

  CC   Function
  ---- ----------
  70   Param 1
  71   Param 2
  72   Param 3
  73   Param 4

------------------------------------------------------------------------

## 🔄 Signal Flow (Simplified)

    INPUT (MIDI / CLOCK)
            ↓
    STEP COUNTER (0–31)
            ↓
    PATTERN MEMORY
            ↓
    VOICE TRIGGERS (B1–B4)
            ↓
    SAMPLE / SYNTH ENGINE
            ↓
    DAC (MCP4901)
            ↓
    AUDIO OUT

------------------------------------------------------------------------

## ⚠️ Limitations

-   32 steps fixed (in firmware)
-   Limited RAM (Arduino Nano)
-   Banks are manually indexed

------------------------------------------------------------------------

## 🛠 Hacking / Modding

To extend pattern length: - increase sequence arrays - change step
counter (0--31 → 0--63/127) - update bank offsets - review memory usage

------------------------------------------------------------------------

## 📜 License

Open hardware / DIY project

------------------------------------------------------------------------

## 💡 Tips

-   Use SHIFT + buttons for live performance
-   Use REC for step recording
-   Try reverse mode for variation
-   Combine banks for longer structures

------------------------------------------------------------------------

## 🚀 TODO

-   64/128 step support
-   OLED display
-   pattern chaining
-   save/load presets
