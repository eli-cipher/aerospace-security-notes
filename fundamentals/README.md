# 🧱 fundamentals/

The ground floor. Before anything can be attacked, you need to know what it actually *is* — how satellites are built, how they talk, and what's physically sitting up there. These notes are kept lean on purpose: short entries, tables, fast to skim.

```
┌─────────────────────────────────────────────────────────────────────┐
│                         📖 READ IN THIS ORDER                        │
└─────────────────────────────────────────────────────────────────────┘

  1️⃣  why-satellite-cybersecurity.md   →  "why should I care at all?"
            │
            ▼
  2️⃣  orbits.md                        →  where satellites sit
            │
            ▼
  3️⃣  satellite-types.md               →  what kinds exist
            │
            ▼
  4️⃣  hardware-components.md           →  what a satellite is made of
            │
            ▼
  5️⃣  software-components.md           →  what runs on that hardware
            │
            ▼
  6️⃣  communication-protocols.md       →  how it talks to the ground
            │
            ▼
  7️⃣  data-formats.md                  →  what that talk looks like
            │
            ▼
  8️⃣  ground-antennas.md               →  what's listening on the ground
            │
            ▼
      🚪 → attack-surface/
```

## 📂 File-by-file

| # | File | One-line definition |
|---|---|---|
| 1 | [`why-satellite-cybersecurity.md`](why-satellite-cybersecurity.md) | Why satellites are a uniquely attractive, uniquely fragile target — infrastructure, physics, and real incidents that prove it. |
| 2 | [`orbits.md`](orbits.md) | The four orbit bands (LEO/MEO/GEO/HEO) — altitude, period, what each is used for, and the security trade-off baked into each. |
| 3 | [`satellite-types.md`](satellite-types.md) | The major categories of satellites by mission — comms, Earth observation, navigation, science, military, and more. |
| 4 | [`hardware-components.md`](hardware-components.md) | The physical subsystems every satellite needs to function — power, thermal, attitude control, propulsion, computer, payload, and more. |
| 5 | [`software-components.md`](software-components.md) | What actually runs on that hardware — flight software architecture, and the industry shift toward shared frameworks like NASA's cFS. |
| 6 | [`communication-protocols.md`](communication-protocols.md) | The protocols that move data on and off a satellite — CCSDS, SpaceWire, DTN — and what's security-relevant about each. |
| 7 | [`data-formats.md`](data-formats.md) | How data is packaged for transmission (telemetry/telecommand, CCSDS packets) and processed after it arrives on the ground. |
| 8 | [`ground-antennas.md`](ground-antennas.md) | The hardware on the ground receiving all of this — antenna types, and the industry shift from dishes to phased arrays. |

## ⏭️ What's next

Once you know what a satellite *is*, the next question is where it can actually be touched. That's [`attack-surface/`](../attack-surface/) — the user, link, and ground segments that surround every satellite system.

---

⬅️ [Back to repo root](../README.md)
