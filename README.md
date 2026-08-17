# Handwired Totem Keyboard

A custom hand-wired build of the **Totem** split ergonomic keyboard. This project leverages the **Supermini NRF52840** for wireless connectivity and features **Horizontal Roller Encoders** for seamless navigation.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c85db919-c958-4709-ad34-945435c07bfc" width="100%" alt="Totem Keyboard Main View" />
</p>

<p align="center">
  <!-- Hàng 1: 3 ảnh -->
  <img src="https://github.com/user-attachments/assets/6ea796ca-0fb8-4ace-aada-1f717dcd3d04" width="30%" />
  <img src="https://github.com/user-attachments/assets/13ee022c-3d65-4a6f-8fdc-f7fd5ac9918a" width="30%" />
  <img src="https://github.com/user-attachments/assets/0d38912d-581d-4dac-b306-2aa4fa8da1a1" width="30%" />
  <br>
  <br>
  <!-- Hàng 2: 2 ảnh -->
  <img alt="1786933312066" src="https://github.com/user-attachments/assets/53a66e0b-e28d-438d-ba79-a15c3db18404" width="45%" />
  <img alt="1786933311960" src="https://github.com/user-attachments/assets/ddb30240-7075-4e98-8334-a17036309060" width="45%" />
</p>

## ✨ Features

- **Wireless Freedom**: Powered by Supermini NRF52840 (ZMK Firmware).
- **Roller Encoders**: Horizontal encoders for smooth scrolling and volume control.
- **Mouse Keys**: Integrated mouse emulation for encoders (`CONFIG_ZMK_POINTING`).
- **Power Efficient**: Optimized for long battery life with `CONFIG_ZMK_SLEEP` disabled for instant wake.
- **Handwired Matrix**: Custom matrix design with direct pins for thumb clusters.

## 🔧 Hardware Components

### Core Components
- **Case**: [Totem_Case](https://drive.google.com/drive/folders/1LL6IALDQxtQ8vZxCIhlPgXplzfOo4yko?usp=sharing)
- **Controller**: 2x Supermini NRF52840.
- **Encoders**: 2x Horizontal Roller Encoder.
- **Switches**: 38x Low profile switches.
- **Diodes**: 38x 1N4148 (19 per side).
- **Battery**: 4x Li-Po Battery ( 2 x lipo 200mah - 60x20x20, 2 x lipo 100mah - 50x10x20)
- **Wiring**: Copper wire or magnet wire.

---

## 🧵 Wiring Guide (Handwired)

This section describes how to wire the **Totem Handwired** keyboard using the **Supermini NRF52840**.
⚠️ **Left and Right halves use different pin assignments. Double-check before soldering.**

---

### 🟢 LEFT HALF

```
            C0     C1     C2     C3     C4
           P0.06  P0.08  P0.17  P0.20  P0.22
             │      │      │      │      │
R0  P0.31 ───┼──────┼──────┼──────┼──────┼── Top row
             │      │      │      │      │
R1  P0.29 ───┼──────┼──────┼──────┼──────┼── Home row
             │      │      │      │      │
R2  P0.02 ───┼──────┼──────┼──────┼──────┼── Bottom row
             │      │
R3  P1.15 ───┼──────┼─────────────── Thumb (inner)

Direct thumb key:
P0.11 ──[SW]── GND
```

---

### 🔴 RIGHT HALF

```
            C0     C1     C2     C3     C4
           P0.22  P0.20  P0.17  P0.08  P0.11
             │      │      │      │      │
R0  P0.31 ───┼──────┼──────┼──────┼──────┼── Top row
             │      │      │      │      │
R1  P0.29 ───┼──────┼──────┼──────┼──────┼── Home row
             │      │      │      │      │
R2  P0.02 ───┼──────┼──────┼──────┼──────┼── Bottom row
             │      │
R3  P1.15 ───┼──────┼─────────────── Thumb (inner)

Direct thumb key:
P1.04 ──[SW]── GND
```
---
## Layout Layers

### 0. Base Layer
Standard QWERTY layout with Home Row Mods on thumbs and outer pinky keys for modifiers.

```text
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │ Q ││ W ││ E ││ R ││ T │      │ Y ││ U ││ I ││ O ││ P │
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │ A ││ S ││ D ││ F ││ G │      │ H ││ J ││ K ││ L ││ ; │
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
   ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮    ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮
   │CTL││ Z ││ X ││ C ││ V ││ B │    │ N ││ M ││ , ││ . ││ / ││SFT│
   ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯    ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯
                   ╭───╮╭───╮╭───╮  ╭───╮╭───╮╭───╮
                   │GUI││TAB││SPC│  │ENT││BSP││DEL│
                   ╰───╯╰─▲─╯╰─▲─╯  ╰─▲─╯╰─▲─╯╰───╯
                          │    │      │    │
                      (Hold) (Hold) (Hold)(Hold)
                       ALT    NAV    SYM   ALT
```

### 1. Nav Layer (Hold Space)
Focused on Numpad (Left) and Navigation/Editing (Right).

```text
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │   ││ 7 ││ 8 ││ 9 ││ 0 │      │PgU││Hom││ ↑ ││End││   │
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │   ││ 4 ││ 5 ││ 6 ││   │      │PgD││ ← ││ ↓ ││ → ││ : │
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
   ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮    ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮
   │   ││   ││ 1 ││ 2 ││ 3 ││ . │    │   ││   ││   ││   ││   ││   │
   ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯    ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯
                   ╭───╮╭───╮╭───╮  ╭───╮╭───╮╭───╮
                   │   ││   ││   │  │   ││   ││DEL│
                   ╰───╯╰───╯╰───╯  ╰───╯╰───╯╰───╯
```

### 2. Sym Layer (Hold Enter)
Programming symbols organized for easy access (Left: Punctuation, Right: Brackets/Math).

```text
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │ ! ││ @ ││ # ││ $ ││ % │      │ ^ ││ & ││ * ││ ( ││ ) │
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │ ~ ││ - ││ + ││ = ││ _ │      │ { ││ } ││ [ ││ ] ││ ' │
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
   ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮    ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮
   │ ` ││   ││   ││   ││   ││   │    │ < ││ > ││   ││   ││ " ││   │
   ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯    ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯
                   ╭───╮╭───╮╭───╮  ╭───╮╭───╮╭───╮
                   │   ││   ││   │  │   ││   ││   │
                   ╰───╯╰───╯╰───╯  ╰───╯╰───╯╰───╯
```

### 3. Adj Layer (Hold Space + Enter)
System controls, Function keys, and Bluetooth management.

```text
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │ F1││ F2││ F3││ F4││ F5│      │ F6││ F7││ F8││ F9││F10│
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
       ╭───╮╭───╮╭───╮╭───╮╭───╮      ╭───╮╭───╮╭───╮╭───╮╭───╮
       │CLR││BT0││BT1││BT2││BT3│      │   ││   ││   ││   ││F11│
       ╰───╯╰───╯╰───╯╰───╯╰───╯      ╰───╯╰───╯╰───╯╰───╯╰───╯
   ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮    ╭───╮╭───╮╭───╮╭───╮╭───╮╭───╮
   │RST││   ││   ││   ││   ││   │    │   ││   ││   ││   ││F12││   │
   ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯    ╰───╯╰───╯╰───╯╰───╯╰───╯╰───╯
                   ╭───╮╭───╮╭───╮  ╭───╮╭───╮╭───╮
                   │   ││   ││   │  │   ││   ││   │
                   ╰───╯╰───╯╰───╯  ╰───╯╰───╯╰───╯
```

## Combos

Simultaneous key presses for quick actions:

* **ESC**: `Q` + `W`
* **DEL**: `O` + `P` (Alternative to Thumb Delete)
* **TOGGLE NAV (Num Lock)**: Space + Enter (Switch to Nav layer permanently for fast number entry).
---

**Notes**

* All matrix keys use **diodes on rows**
* Encoder: `P1.13 / P1.11`, center pin → GND

## 📦 Installation
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
