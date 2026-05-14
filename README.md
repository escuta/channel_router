# Channel Router

A passive 3-position signal routing box for analogue audio, allowing selection between left channel only, stereo (both channels), or right channel only.

## Use Case

For systems where a single speaker is desired for mono listening, or where channel selection is needed without altering preamplifier settings. Sits between a preamplifier and power amplifier(s). Particularly useful when used in conjunction with a preamplifier's built-in mono switch: engage the mono switch on the preamp, then use this box to select which speaker to listen from.

## Signal Chain

```
Preamplifier outputs (L + R) → [this box] → Power amplifier inputs (L + R)
```

## Circuit Description

A passive signal router using a 2P3T rotary switch. One pole switches the left channel, the other switches the right channel. Both poles operate simultaneously.

- **Position 1 (Left):** L IN routed to L OUT only. R OUT earthed via 1kΩ resistor. Left speaker only.
- **Position 2 (Stereo):** L IN routed to L OUT. R IN routed to R OUT. Normal stereo passthrough.
- **Position 3 (Right):** R IN routed to R OUT only. L OUT earthed via 1kΩ resistor. Right speaker only.

No active components. Signal path in stereo mode is wire and switch contact only. The 1kΩ bleed resistors prevent the unused power amplifier input from floating in mono positions. Effect on signal level is less than 0.01dB.

## Components

| Component | Value/Type | Qty |
|-----------|-----------|-----|
| RCA panel mount sockets | insulated from enclosure | 4 |
| Resistors | 1kΩ | 2 |
| Rotary switch | 2P3T | 1 |
| Aluminium enclosure | elongated, ~10cm between faces | 1 |

## Enclosure Layout

- **Back face**: L OUT (top left), R OUT (top right), L IN (bottom left), R IN (bottom right) — all RCA, viewed from outside
- **Front face**: rotary switch with knob, centre of face

Hole centres for RCA sockets: 15mm from each edge on a 55×55mm face (25mm between centres).

**Important:** RCA socket bodies must be electrically isolated from the enclosure using insulating washers. Earth the enclosure at one deliberate point only via the earth bus if desired, or leave it floating.

## Switch Wiring — 2P3T

```
Pole 1 — Left channel:
  COM1        ← L IN hot
  Left throw  → L OUT hot
  Centre throw→ L OUT hot
  Right throw → earth bus (L OUT earthed via 1kΩ in pos 3)

Pole 2 — Right channel:
  COM2        ← R IN hot
  Left throw  → earth bus (R OUT earthed via 1kΩ in pos 1)
  Centre throw→ R OUT hot
  Right throw → R OUT hot
```

Use a multimeter in continuity mode to identify which throw corresponds to which knob position before soldering.

## Wiring Instructions

Wire colours used: blue = left channel hot, red = right channel hot, green = earth.

### Back panel — RCA sockets

1. Solder blue wire (22cm) to L IN hot pin — will run to COM1 on switch
2. Solder red wire (22cm) to R IN hot pin — will run to COM2 on switch
3. Solder blue wire (22cm) to L OUT hot pin — will run to Pole 1 left throw
4. Solder blue wire (22cm) to L OUT hot pin — will run to Pole 1 centre throw
5. Solder red wire (22cm) to R OUT hot pin — will run to Pole 2 right throw
6. Solder red wire (22cm) to R OUT hot pin — will run to Pole 2 centre throw
7. Solder one leg of 1kΩ resistor A to L OUT hot pin, other leg to green earth chain
8. Solder one leg of 1kΩ resistor B to R OUT hot pin, other leg to green earth chain
9. Daisy-chain all four RCA sleeve pins with short green wire (22cm total, soldered at each pin) — L OUT sleeve → R OUT sleeve → R IN sleeve → L IN sleeve

### Front panel — switch pins

10. Solder blue wire from L IN hot (step 1) to COM1
11. Solder red wire from R IN hot (step 2) to COM2
12. Solder blue wire from L OUT hot (step 3) to Pole 1 left throw
13. Solder blue wire from L OUT hot (step 4) to Pole 1 centre throw
14. Solder red wire from R OUT hot (step 5) to Pole 2 right throw
15. Solder red wire from R OUT hot (step 6) to Pole 2 centre throw
16. Solder green wire (22cm) from Pole 1 right throw to green earth chain on back panel
17. Solder green wire (22cm) from Pole 2 left throw to green earth chain on back panel
18. Leave any additional poles or pins on the switch unconnected

### Verification before closing

19. Knob left — L IN hot → L OUT hot: continuity. L IN hot → R OUT hot: no continuity. R IN hot → R OUT hot: no continuity.
20. Knob centre — L IN hot → L OUT hot: continuity. R IN hot → R OUT hot: continuity. L IN hot → R OUT hot: no continuity.
21. Knob right — R IN hot → R OUT hot: continuity. R IN hot → L OUT hot: no continuity. L IN hot → L OUT hot: no continuity.
22. Confirm earth chain has continuity across all four RCA sleeves.

**Test at the RCA sockets, not at the switch pins** — testing at the switch with wiring in place gives misleading results due to back panel connections creating apparent continuity between throws.

## Files

| File | Description |
|------|-------------|
| `channel_router.svg` | Circuit schematic |
| `README.md` | This file |

## Licence

[PolyForm Noncommercial 1.0](https://polyformproject.org/licenses/noncommercial/1.0.0/)
