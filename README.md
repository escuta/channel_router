# Channel Router

A passive 3-position signal routing box for analogue audio, allowing selection between left channel only, both channels (stereo), or right channel only.

## Use Case

For systems where a single speaker is desired for mono listening, or where channel selection is needed without altering preamp settings. Sits between a preamplifier and power amplifier(s).

## Signal Chain

```
Preamplifier outputs (L + R) → [this box] → Power amplifier inputs (L + R)
```

## Circuit Description

A passive signal router using a 1P3T rotary switch. The selected channel is routed to the appropriate output. In the left or right mono positions, the unused output is grounded via a 100Ω resistor to prevent the power amplifier input from floating.

- **Position 1 (Left):** Left channel signal routed to left output. Right output grounded via 100Ω. Left speaker only.
- **Position 2 (Both):** Left to left output, right to right output. Normal stereo passthrough.
- **Position 3 (Right):** Right channel signal routed to right output. Left output grounded via 100Ω. Right speaker only.

No active components. Signal path in stereo mode is wire and switch contact only.

## Components

| Component | Value/Type | Qty |
|-----------|-----------|-----|
| RCA panel mount sockets | — | 4 |
| Resistors | 100Ω | 2 |
| Rotary switch | 1P3T | 1 |
| Aluminium enclosure | Hammond 1590B style, 112×60×31mm | 1 |

## Enclosure Layout

- **Connections face**: L IN, R IN, L OUT, R OUT (RCA)
- **Switch face**: 1P3T rotary switch with knob (opposite face)

## Switch Wiring — 1P3T

The 1P3T rotary switch has one common pin and three throw pins:

```
Common → Left input signal tap

Throw 1 (pos 1) → Left output hot
Throw 2 (pos 2) → both Left and Right output hots (stereo passthrough)
Throw 3 (pos 3) → Right output hot
```

In positions 1 and 3, the unused output is connected to ground via a 100Ω resistor
to prevent the amplifier input from floating.

Use a multimeter in continuity mode to confirm throw positions before soldering.

## Files

| File | Description |
|------|-------------|
| `channel_router.svg` | Circuit schematic |
| `README.md` | This file |
