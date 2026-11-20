# 🎯 attack-surface/

A satellite system isn't one thing to attack — it's several, spread across a chain that stretches from a user's handheld device all the way up to orbit. This folder maps that chain using a standard **4-segment model**, and covers where a real-world attacker can actually touch it.

```
┌──────────────────────────────────────────────────────────────────────────┐
│                      🛰️  THE 4-SEGMENT ATTACK-SURFACE MODEL               │
└──────────────────────────────────────────────────────────────────────────┘

   👤 USER SEGMENT          📡 LINK SEGMENT          🖥️ GROUND SEGMENT         🚀 SPACE SEGMENT
   (terminals, modems,      (the RF path             (mission control,         (the satellite
    receivers people          between user            antennas, network         itself)
    actually touch)           & satellite)             operations)
          │                        │                        │                        │
          ▼                        ▼                        ▼                        ▼
   covered in this          covered in this          covered in this          deferred to
   folder                   folder                   folder                   offensive-techniques/
```

**Why space segment is deferred:** attacking the satellite itself (its onboard bus, command authority, subsystems) needs the groundwork this folder lays first — you have to understand how the other three segments get you *there*. That's exactly what [`offensive-techniques/`](../offensive-techniques/) covers in depth.

## 📂 File-by-file

| Segment | File | One-line definition |
|---|---|---|
| 👤 User | [`user-segment.md`](user-segment.md) | The terminals and modems people actually hold or operate — often the weakest link, thanks to hardcoded credentials and exposed debug interfaces. |
| 📡 Link | [`link-segment.md`](link-segment.md) | The radio-frequency path between a terminal and the satellite — where jamming and signal-strength asymmetries make denial-of-service cheap and effective. |
| 🖥️ Ground | [`ground-segment.md`](ground-segment.md) | Mission control, antennas, and the networks running them — arguably the biggest risk, since it never leaves the ground and inherits every ordinary IT weakness. |

## 📖 Read in this order

```
user-segment.md  →  link-segment.md  →  ground-segment.md
  "what you         "the signal          "the operators
   touch"             in between"         running it all"
```

Each file builds a slightly bigger picture of how exposed the system really is before any attacker even reaches the spacecraft itself.

## ⏭️ What's next

Once you understand *where* a satellite system can be reached, [`offensive-techniques/`](../offensive-techniques/) covers *how* — the specific methods that chain across these segments toward real command-and-control of a satellite.

---

⬅️ [Back to repo root](../README.md)
