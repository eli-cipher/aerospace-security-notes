# Communication Protocols

Software (see [`software-components.md`](software-components.md)) needs a shared language to actually talk — both to the ground, and between its own internal components. These aren't all the same layer: some protocols govern the link to Earth, some run entirely inside the spacecraft, and some solve the unique problem of a connection that isn't always there.

---

## Quick reference

| Protocol | Layer | What it does | Security-relevant note |
|---|---|---|---|
| **CCSDS** | Ground ↔ space | The umbrella standard for telemetry/telecommand packets, RF modulation, timing, and data formats | A shared, widely-adopted standard — a weakness found in a CCSDS implementation isn't a one-mission problem, it's potentially relevant across 200+ missions using it |
| **SpaceWire** | Onboard (internal) | Connects a satellite's own internal components — OBC, instruments, mass memory — to each other | Not exposed to the ground directly, but a foothold anywhere onboard (e.g. via a compromised instrument) can potentially reach other components over this same internal bus |
| **DTN** | Networking layer | Moves data reliably across links that are slow, delayed, or not always connected | Store-and-forward means data sits on intermediate nodes before reaching its destination — more places along the path where it could be intercepted or tampered with |

---

### 🌐 CCSDS — the umbrella standard

The **Consultative Committee for Space Data Systems** isn't a single protocol, it's an international standards body (formed in 1982 by major space agencies) that defines a shared set of protocols so agencies and missions don't each have to build incompatible, custom "black box" systems from scratch.

What it standardizes: packet telemetry and telecommand formats, RF modulation schemes, timing formats, lossless data compression, and more — published as free, public "Blue Book" recommendations. The payoff is real interoperability: agencies can share ground stations and support each other's missions because everyone is speaking a common protocol.

**Adoption**: over 200 satellite missions have used CCSDS protocols, with 10 member space agencies and 100+ industrial associates worldwide. This is effectively the TCP/IP of space — not universal, but close to the default.

### 🔗 SpaceWire — the onboard bus

Easy to mix up with a ground-link protocol, but SpaceWire is the opposite: it's entirely internal, connecting a satellite's own components to each other — the onboard computer, instruments, and mass memory — not the satellite to Earth.

It uses point-to-point serial links (bidirectional, low latency, low error rate) with wormhole-switch routing between nodes. Became an official standard (ECSS-E-ST-50-12C) in 2003 and is used on real missions like ESA's BepiColombo. Its appeal is practical: simple circuitry, low power draw, and components built for one mission can be reused on the next.

### 🛰️ DTN — handling a connection that isn't always there

Ordinary internet protocols like TCP/IP assume a mostly-continuous path between sender and receiver. Space breaks that assumption constantly — long delays (minutes to hours depending on distance) and links that drop out entirely when a satellite passes out of view of a ground station.

**Delay/Disruption Tolerant Networking** solves this with a "store-and-forward" model, built around the Bundle Protocol: data gets packaged into "bundles," and any intermediate node along the way holds onto a bundle until the next hop is actually available, instead of assuming it can be delivered immediately. Delivery can be made reliable hop-by-hop, without needing instant feedback from the final destination. NASA's PACE mission uses this in practice — housekeeping data gets bundled, sent through whichever ground station is available, and reassembled only once it reaches the mission operations center.

---

**Next:** [`data-formats.md`](data-formats.md) — what's actually carried inside these protocols: the telemetry, command, and payload data itself.
