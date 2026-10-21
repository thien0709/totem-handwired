# Totem Keyboard ZMK Keymap

A custom hand-wired build of the **Totem** split ergonomic keyboard. This project leverages the **Supermini NRF52840** for wireless connectivity and features **Horizontal Roller Encoders** for seamless navigation.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c50f8c00-dadd-4662-810c-7f6dee25dd39" width="100%" alt="Totem Keyboard Main View" />
</p>

<p align="center">
  <img width="1020" height="1020" alt="cc52432b740cf452ad1d" src="https://github.com/user-attachments/assets/d9c59ff1-d332-4bff-9159-ee9027d32570" />
  <img src="https://github.com/user-attachments/assets/53a66e0b-e28d-438d-ba79-a15c3db18404" width="49%" alt="Totem Keyboard Detail 1" />
  <img src="https://github.com/user-attachments/assets/0d38912d-581d-4dac-b306-2aa4fa8da1a1" width="49%" alt="Totem Keyboard Detail 2" />
</p>

---
##  Hardware Components

### Core Components
- **Case**: [Totem_Case](https://drive.google.com/drive/folders/1gwYmMvKHHdeVcXvl8slok06qVYsDDdrA?usp=sharing)
- **Controller**: 2x Supermini NRF52840.
- **Encoders**: 2x Horizontal Roller Encoder.
- **Switches**: 38x Low profile switches.
- **Diodes**: 38x 1N4148 (19 per side).
- **Ceramic Capacitor**: 4x 100nF (Code 104) (2 per side)
- **Battery**: 4x Li-Po Battery ( 2 x lipo 200mah - 60x20x20, 6 x lipo 100mah - 50x10x20)
- **Wiring**: Copper wire .

---

##  Wiring Guide (Handwired)

This section describes how to wire the **Totem Handwired** keyboard using the **Supermini NRF52840**.

4-row × 5-column matrix with `diode-direction = "col2row"`
(columns are outputs, rows are pull-down inputs; diodes run from column to row).

### LEFT HALF

```
            C0      C1      C2      C3      C4
           P1.13   P1.15   P0.02   P0.29   P0.31
             │       │       │       │       │
R0  P0.17 ───●───────●───────●───────●───────●── Top row
             │       │       │       │       │
R1  P0.20 ───●───────●───────●───────●───────●── Home row
             │       │       │       │       │
R2  P0.22 ───●───────●───────●───────●───────●── Bottom row
             │       │       │       │       │
R3  P0.24 ───●───────○───────●───────●───────●── Thumb row
```

### RIGHT HALF (columns reversed relative to left, `col-offset = 5`)

```
            C0      C1      C2      C3      C4
           P0.31   P0.29   P0.02   P1.15   P1.13
             │       │       │       │       │
R0  P0.17 ───●───────●───────●───────●───────●── Top row
             │       │       │       │       │
R1  P0.20 ───●───────●───────●───────●───────●── Home row
             │       │       │       │       │
R2  P0.22 ───●───────●───────●───────●───────●── Bottom row
             │       │       │       │       │
R3  P0.24 ───●───────●───────●───────○───────●── Thumb row
```

● = key present (per `default_transform`), ○ = no key.

### Direct key & encoder (identical on both halves)

| Component        | Pin   | Notes                                    |
|------------------|-------|------------------------------------------|
| Thumb direct key | P1.11 | Switch to GND, `GPIO_ACTIVE_LOW`, pull-up |
| Encoder A        | P0.11 | Pull-up                                  |
| Encoder B        | P1.04 | Pull-up                                  |

---
## 0. Base Layer
Standard QWERTY layout with Home Row Mods on thumbs and outer pinky keys for modifiers.

```text
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │ Q │ │ W │ │ E │ │ R │ │ T │       │ Y │ │ U │ │ I │ │ O │ │ P │
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │ A │ │ S │ │ D │ │ F │ │ G │       │ H │ │ J │ │ K │ │ L │ │ ; │
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
│CTL│ │ Z │ │ X │ │ C │ │ V │ │ B │       │ N │ │ M │ │ , │ │ . │ │ / │ │SFT│
╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
                        ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮
                        │GUI│ │TAB│ │SPC│       │ENT│ │BSP│ │DEL│
                        ╰───╯ ╰─▲─╯ ╰─▲─╯       ╰─▲─╯ ╰─▲─╯ ╰───╯
                                │     │           │     │
                             (Hold) (Hold)     (Hold) (Hold)
                               ALT   NAV         SYM   ALT
```

## 1. Nav Layer *(Hold Space)*
Focused on Numpad (Left) and Navigation/Editing (Right).

```text
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │   │ │ 7 │ │ 8 │ │ 9 │ │ 0 │       │PgU│ │Hom│ │ ↑ │ │End│ │   │
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │   │ │ 4 │ │ 5 │ │ 6 │ │   │       │PgD│ │ ← │ │ ↓ │ │ → │ │ : │
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
│   │ │   │ │ 1 │ │ 2 │ │ 3 │ │ . │       │   │ │   │ │   │ │   │ │   │ │   │
╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
                        ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮
                        │   │ │   │ │   │       │   │ │   │ │DEL│
                        ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯
```

## 2. Sym Layer *(Hold Enter)*
Programming symbols organized for easy access (Left: Punctuation, Right: Brackets/Math).

```text
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │ ! │ │ @ │ │ # │ │ $ │ │ % │       │ ^ │ │ & │ │ * │ │ ( │ │ ) │
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │ ~ │ │ - │ │ + │ │ = │ │ _ │       │ { │ │ } │ │ [ │ │ ] │ │ ' │
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
│ ` │ │   │ │   │ │   │ │   │ │   │       │ < │ │ > │ │   │ │   │ │ " │ │   │
╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
                        ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮
                        │   │ │   │ │   │       │   │ │   │ │   │
                        ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯
```

## 3. Adj Layer *(Hold Space + Enter)*
System controls, Function keys, and Bluetooth management.

```text
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │ F1│ │ F2│ │ F3│ │ F4│ │ F5│       │ F6│ │ F7│ │ F8│ │ F9│ │F10│
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
      ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
      │CLR│ │BT0│ │BT1│ │BT2│ │BT3│       │   │ │   │ │   │ │   │ │F11│
      ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮ ╭───╮
│RST│ │   │ │   │ │   │ │   │ │   │       │   │ │   │ │   │ │   │ │F12│ │   │
╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯
                        ╭───╮ ╭───╮ ╭───╮       ╭───╮ ╭───╮ ╭───╮
                        │   │ │   │ │   │       │   │ │   │ │   │
                        ╰───╯ ╰───╯ ╰───╯       ╰───╯ ╰───╯ ╰───╯
```
## Rotary Encoders
Configurations for the rotary encoders based on the active layer (configured via `sensor-bindings` in ZMK).

```text
    [Left Horizontal Roller]            [Right Horizontal Roller]
         +-----------+                       +-----------+
  Scroll |     ^     |                Scroll |     ^     |  Scroll
  Up     |     |     |  Scroll        Up     |     |     |  Up
         |  (roller) |  Up                   |  (roller) |
  Scroll |     |     |  Scroll        Scroll |     |     |  Scroll
  Down   |     v     |  Down          Down   |     v     |  Down
         +-----------+                       +-----------+
```
| Layer          | Turn Up (▲)        | Turn Down (▼)      |
|:---------------|:-------------------|:-------------------|
| **0. Base**    | Scroll Up          | Scroll Down        |
| **1. Nav**     | Volume Up          | Volume Down        |
| **2. Sym**     | Volume Up          | Volume Down        |
| **3. Adj**     | Volume Up          | Volume Down        |
## Combos
Simultaneous key presses for quick actions:

| Combo Action           | Keys Pressed     | Description                                           |
|:-----------------------|:-----------------|:------------------------------------------------------|
| **ESC**                | `Q` + `W`        | Quick access to Escape.                               |
| **DEL**                | `O` + `P`        | Delete (Alternative to Thumb Delete).                 |
| **TOGGLE NAV**         | `Space` + `Enter`| Switch to Nav layer permanently for fast number entry.|

##  Installation
1. Download and extract the [Totem Firmware](https://github.com/thien0709/Totem_Handwired/releases/tag/firmware)
2. **Enter Bootloader:**
   Connect the keyboard to your PC via USB. Quickly **double-tap the Reset button**. A storage drive named `NICENANO` will appear on your computer.
3. **Flash Firmware:**
   Drag and drop the corresponding `.uf2` file into the `NICENANO` drive.
   * Use the `settings_reset-nice_nano_v2-zmk.uf2` file for reset **Left** and **Right** keyboard.
   * Use the `totem_hw_left-nice_nano_v2-zmk.uf2` file for the **Left** keyboard.
   * Use the `totem_hw_right-nice_nano_v2-zmk.uf2` file for the **Right** keyboard.
   *(The drive will automatically close, and the keyboard will reboot when finished).*
5. **Sync (Pairing):**
   After flashing both sides, unplug the USB. Turn on battery power for both halves. Press the **Reset button once on both sides** at the same time to let them pair wirelessly.
