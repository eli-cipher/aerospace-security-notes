# Ground Antennas

Everything so far has been about the satellite's side. This is the other end — the hardware on the ground that actually sends and receives what's been described in [`communication-protocols.md`](communication-protocols.md) and [`data-formats.md`](data-formats.md). Five antenna types cover nearly all of it.

---

| Type | One-line description | Typical use | Key trade-off |
|---|---|---|---|
| **📡 Parabolic (dish)** | A curved reflector that concentrates signal into a high-gain beam | High-capacity comms, Earth-observation downlinks, deep-space links, radar | Narrow beam needs precise pointing — easy to lose signal if misaimed |
| **📶 Phased array** | Many small elements, electronically steered by controlling phase/amplitude — no moving parts | Tracking fast-moving LEO constellations, multi-beam satellite links | Agility costs complexity — many RF paths, heavy calibration, power, and software demands |
| **🌀 Helix** | Axial-mode antenna giving circular polarization and moderate gain | Small-spacecraft links needing more bandwidth than a patch provides | Protruding shape complicates launch packaging and mechanical durability |
| **▪️ Patch** | Thin, flat, printed-circuit antenna — simple and light | CubeSats, GNSS receivers, telemetry systems, planar arrays | Limited bandwidth, and performance can shift once mounted/integrated |
| **📯 Horn** | Simple, efficient antenna with well-controlled patterns and good power handling | Standalone links, reflector feeds, calibration | Physically large at lower frequencies; high-frequency versions need tight manufacturing tolerances |

---

## Why the ground is shifting away from dishes

The classic image of a satellite ground station is a big, mechanically-steered dish. That model is struggling to keep up with how satellites are actually operating today.

A traditional dish has to physically rotate to track a satellite — fine for one GEO satellite sitting in a fixed spot, much harder for a constellation of fast-moving LEO satellites passing overhead every few minutes, the way Starlink or Kuiper operate. Mechanical tracking adds latency, leaves the dish idle between passes, and simply can't scale to tracking many satellites at once.

Phased arrays solve the speed problem — they steer electronically, instantly, with no moving parts — but a single phased array struggles to match a large dish's raw gain without burning a lot more power and cost. Current research is exploring combining several smaller, low-cost phased arrays together to get dish-level performance with array-level flexibility, aiming to track multiple satellites simultaneously instead of one at a time.

**Real examples already doing this at scale**: Starlink's own user terminal is an electronically-steered phased array (roughly 110° field of view, 75-100W average power), and Amazon's satellite broadband system (Project Kuiper, renamed Amazon Leo in late 2025) uses flat-panel Ka-band phased-array terminals too — the shift isn't theoretical, it's already how the largest constellations connect to the ground.

---

This closes out the fundamentals: you now have the vocabulary and mental model for what a satellite is, where it sits, what it's built from, and how it talks to Earth.

**Next:** [`attack-surface/`](../attack-surface/) — the same systems, now asked *where can this actually be touched by an attacker?*
