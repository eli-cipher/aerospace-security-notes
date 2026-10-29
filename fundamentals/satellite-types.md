# Satellite Types

Same orbit, very different satellite. What a satellite is built to *do* shapes its hardware, its software, and — later in this repo — its attack surface. Six categories cover almost everything in orbit today.

---

### 📡 Communications

Relay voice, data, and internet signals between ground points too far apart (or too remote) for direct line-of-sight links.

**Typically found in:** LEO (broadband constellations) or GEO (fixed regional coverage)
**Examples:** Starlink, OneWeb, Intelsat

---

### 🌍 Earth Observation

Image or sense the planet's surface and atmosphere — weather, environmental change, land use, natural resources, disaster monitoring.

**Typically found in:** LEO, often sun-synchronous for consistent lighting across passes
**Examples:** Landsat, Sentinel (Copernicus program)

---

### 🧭 Navigation

Broadcast precise timing and positioning signals that receivers on the ground (or in the air/sea) use to calculate location.

**Typically found in:** MEO
**Examples:** GPS, GLONASS, Galileo

---

### 🔬 Scientific

Carry instruments for research — astronomy, space physics, Earth science — rather than delivering a day-to-day operational service.

**Typically found in:** varies widely — LEO, GEO, deep space, or Lagrange points depending on the mission
**Examples:** Hubble, James Webb Space Telescope (JWST)

---

### 🛡️ Military

Reconnaissance, surveillance, secure communications, and early warning, operated by or for defense forces.

**Typically found in:** varies by mission — LEO for imaging/reconnaissance, HEO/GEO for persistent communications coverage
**Examples:** Reconnaissance programs are rarely publicly detailed by design — the KH ("Keyhole") series is one of the few historically acknowledged examples

---

### 📦 CubeSats & Small Satellites

Standardized small satellites, not defined by mission but by a common form factor — makes them cheap to build and easy to launch as secondary payloads.

| | |
|---|---|
| **Standard unit (1U)** | ~10×10×11.35 cm, ≤2 kg |
| **Common sizes** | 1U, 3U (most common — 40%+ of nanosats launched), 6U, 12U |
| **Rough cost** | ~$50–60K to build and launch a basic 1U |
| **Used for** | Earth observation, technology testing, education, even deep-space missions (e.g. MarCO's 6U cubesats to Mars) |

**Why they matter here:** the same low cost and standardization that made cubesats a democratizing force in spaceflight also makes them relevant later in this repo — a cheap, easy-to-launch platform is also an easy platform for an attacker to get into orbit.

---

**Next:** [`hardware-components.md`](hardware-components.md) — now that you know *what kind* of satellite you're looking at, what it's physically built out of underneath.
