# aerospace-security-notes

A beginner-friendly study resource for aerospace and satellite cybersecurity — structured to take someone from zero to real offensive technique, one level at a time, without needing ten scattered sources to piece it together.

Notes are written in plain language, in the author's own words, synthesized across multiple sources. Full source list: [`sources.md`](sources.md).

**Author:** Eli Cipher

## Reading order

```
fundamentals/  →  attack-surface/  →  offensive-techniques/
   what it is       where it's weak      how it's broken
```

| Folder | Covers | Depth |
|---|---|---|
| [`fundamentals/`](fundamentals/) | Orbits, satellite types, hardware/software components, comms protocols, data formats, ground antennas | Lean — short entries, tables |
| [`attack-surface/`](attack-surface/) | The 4-segment model (user, link, ground, space) — where a satellite system can be touched, and why | Moderate |
| [`offensive-techniques/`](offensive-techniques/) | Signal interception, jamming, spoofing, C2 hijacking, satellite bus attacks, VSAT attacks, replay/telemetry tampering | Deep |

Go in order — each section builds on the last. Each folder has its own `README.md` with the exact file-by-file read order inside it. Already know the basics? Skim `fundamentals/` and start at `attack-surface/`.

## Structure

```
aerospace-security-notes/
├── fundamentals/
├── attack-surface/
├── offensive-techniques/
└── sources.md
```

## Scope note

`offensive-techniques/` covers real attack methodology, for understanding how satellite systems actually get broken — not a how-to for unauthorized access. Use only against systems you own or are authorized to test.

## Status

✅ Complete — all 18 notes across `fundamentals/`, `attack-surface/`, and `offensive-techniques/` are written. See `sources.md` for the full list of what was consulted.
