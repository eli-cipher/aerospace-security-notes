# Orbits

Where a satellite sits in space shapes almost everything about it — how fast it moves, how often it passes overhead, how far its signal has to travel, and which attacks are even realistic against it. Four orbit classes cover nearly everything in use today.

---

### LEO — Low Earth Orbit

| | |
|---|---|
| **Altitude** | 200 – 2,000 km |
| **Orbital period** | ~90 – 127 min |
| **Used for** | Broadband internet constellations, Earth imaging, crewed stations |
| **Examples** | Starlink, ISS, Planet |

**Why this orbit:** Close to Earth means a strong signal and low latency — good enough for real-time broadband and sharp imaging.
**Trade-off:** A single satellite only covers a small patch of Earth and moves fast across the sky, so useful coverage needs a large constellation, not one satellite.

> Security note: shortest signal path of any orbit class — weakest free-space path loss, meaning signals arrive strongest and are comparatively easier to intercept or jam at range.

---

### MEO — Medium Earth Orbit

| | |
|---|---|
| **Altitude** | 2,000 – 35,786 km |
| **Orbital period** | ~2 – 24 hours |
| **Used for** | Satellite navigation |
| **Examples** | GPS, Galileo, GLONASS |

**Why this orbit:** A sweet spot between coverage and visibility — fewer satellites than LEO are needed for global coverage, and the geometry suits precise positioning.
**Trade-off:** Signals travel much farther than LEO, arriving weaker — part of why GPS jamming/spoofing is physically easier than it sounds.

> Security note: this is the orbit class behind every GPS-spoofing and GNSS-jamming story — long signal travel distance means low received signal strength on the ground.

---

### GEO — Geostationary Orbit

| | |
|---|---|
| **Altitude** | 35,786 km |
| **Orbital period** | ~24 hours (matches Earth's rotation) |
| **Used for** | Television broadcast, weather monitoring, telecommunications |
| **Examples** | GOES, Intelsat, SES |

**Why this orbit:** Matching Earth's rotation means the satellite appears fixed in the sky — one satellite gives continuous coverage of the same region, no tracking antenna needed on the ground.
**Trade-off:** Fixed over the equator, so coverage weakens toward the poles, and the long round-trip distance adds noticeable signal delay.

> Security note: a GEO satellite can see roughly a third of Earth's surface at once — its signal is reachable from dozens of countries simultaneously, which is part of why jurisdiction over satellite signals is hard to enforce.

---

### HEO — Highly Elliptical Orbit

| | |
|---|---|
| **Altitude** | ~600 km perigee → ~39,700 km apogee (e.g. Molniya orbit) |
| **Orbital period** | ~12 hours (Molniya) |
| **Used for** | High-latitude communications, early warning, military/classified surveillance |
| **Examples** | Molniya, Tundra |

**Why this orbit:** GEO satellites sit over the equator and appear low (or invisible) from far-northern latitudes above ~81°. A highly elliptical, inclined orbit spends most of its time lingering near a high-latitude apogee, giving strong coverage over places like Russia, Canada, and northern Europe that GEO can't serve well.
**Trade-off:** One satellite isn't enough for continuous coverage — needs a constellation (3+) handing off coverage as each satellite swings through its orbit, plus ground stations need steerable antennas to track it.

> Security note: an elliptical, shifting ground track makes a HEO satellite a moving target — harder to continuously intercept than a fixed GEO satellite, but the frequent antenna hand-offs and ground-tracking requirements add their own attack surface.

---

**Next:** [`satellite-types.md`](satellite-types.md) — now that you know *where* satellites sit, what kinds of satellites actually occupy these orbits.
