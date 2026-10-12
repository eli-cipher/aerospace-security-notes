# 🛰️ fundamentals/

The starting point. Short, lean entries that build the vocabulary and mental model you need before any of this repo's security content will make sense.

---

## 🧭 The Flow

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                         │
│   1. WHY           2. ORBITS        3. SATELLITE       4. HARDWARE      │
│   it matters   →    LEO/MEO/    →     TYPES        →    bus, power,     │
│   at all             GEO/HEO         comms/EO/nav       ADCS, payload   │
│                                                                         │
│                                                               │         │
│        ┌──────────────────────────────────────────────────────┘         │
│        ▼                                                                │
│   5. SOFTWARE      6. COMMS          7. DATA           8. GROUND        │
│   flight SW,   →    PROTOCOLS    →    FORMATS      →    ANTENNAS        │
│   AOCS, telemetry   CCSDS, DTN...    telemetry/cmd      parabolic, etc. │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
            satellite + orbit  →  what it's built of  →  how it talks  →  how ground hears it
```

Each file assumes the one(s) before it. Read top to bottom, left to right — don't skip ahead.

**Already comfortable with the basics?** Skim this folder and jump straight to [`attack-surface/`](../attack-surface/).

---

## 📂 File-by-file

| # | File | What it covers | Why it's here |
|:-:|---|---|---|
| 1 | 🎯 [`why-satellite-cybersecurity.md`](why-satellite-cybersecurity.md) | Why satellites are worth securing, and why this is a different problem from ordinary IT/network security | The motivation for everything that follows — the only file in this folder that earns real depth |
| 2 | 🌍 [`orbits.md`](orbits.md) | LEO / MEO / GEO / HEO — altitude, orbital period, typical use | Orbit choice shapes almost everything downstream: revisit rate, latency, which attacks are even feasible |
| 3 | 🛰️ [`satellite-types.md`](satellite-types.md) | Comms, Earth observation, navigation, scientific, military, cubesats | What kind of satellite you're even looking at, and what it's built to do |
| 4 | ⚙️ [`hardware-components.md`](hardware-components.md) | Bus, power, propulsion, ADCS, payload, onboard computing | The physical "body" every satellite needs, regardless of type |
| 5 | 🧠 [`software-components.md`](software-components.md) | Flight software, AOCS software, telemetry/command handling | The "mind" that runs the hardware from file 4 |
| 6 | 📡 [`communication-protocols.md`](communication-protocols.md) | CCSDS, SpaceWire, DTN, and the rest | Where the satellite's hardware/software meets the outside world |
| 7 | 📦 [`data-formats.md`](data-formats.md) | Telemetry, command, scientific, and navigation data | What's actually carried inside the communications from file 6 |
| 8 | 📶 [`ground-antennas.md`](ground-antennas.md) | Parabolic, phased array, helix, patch, horn | How the ground side receives/sends those signals — closes the loop back to Earth |

---

## 🤔 Why this order

The sequence roughly traces a signal's own journey:

> **what is this satellite, and where is it** → **what kind of satellite is it** → **what it's physically made of** → **what runs that hardware** → **how it talks to the ground** → **what that talk actually carries** → **how the ground receives it**

By the end of this folder, you should be able to describe that whole journey yourself — without a source open next to you.

---

➡️ **Next up:** [`attack-surface/`](../attack-surface/) — same systems, now asked *"where can this actually be touched by an attacker?"*
