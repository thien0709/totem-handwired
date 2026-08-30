# Totem Keyboard ZMK Keymap

Custom ZMK keymap configuration for the Totem split ergonomic keyboard, featuring a 38-key layout, rotary encoders, and a 4-layer system.

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
       [Left Rotary Encoder]                 [Right Rotary Encoder]
           ╭───────╮                             ╭───────╮
           │   ⤿   │                             │   ⤾   │
       ⤹ ──┤   ◎   ├── ⤸                     ⤹ ──┤   ◎   ├── ⤸
           │   ⤾   │                             │   ⤿   │
           ╰───────╯                             ╰───────╯

| Layer          | Turn Left (⤹)      | Turn Right (⤸)     |
|:---------------|:-------------------|:-------------------|
| **0. Base**    | Scroll Up          | Scroll Down        |
| **1. Nav**     | Volume Down        | Volume Up          |
| **2. Sym**     | Volume Down        | Volume Up          |
| **3. Adj**     | Volume Down        | Volume Up          |
```

## Combos
Simultaneous key presses for quick actions:

| Combo Action           | Keys Pressed     | Description                                           |
|:-----------------------|:-----------------|:------------------------------------------------------|
| **ESC**                | `Q` + `W`        | Quick access to Escape.                               |
| **DEL**                | `O` + `P`        | Delete (Alternative to Thumb Delete).                 |
| **TOGGLE NAV**         | `Space` + `Enter`| Switch to Nav layer permanently for fast number entry.|
