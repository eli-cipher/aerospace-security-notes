# 🎯 attack-surface/

Don't start here. This folder assumes [`fundamentals/`](../fundamentals/) — every attack vector below is explained in terms of a component or protocol defined there.

This is where the repo turns from *"what a satellite system is"* into actual security thinking, using the standard **4-segment model**.

---

## 🧭 The Flow

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│   1. USER SEGMENT        2. LINK SEGMENT         3. GROUND SEGMENT   │
│   terminals, user    →   the RF uplink/      →    mission control,   │
│   equipment               downlink in between      ground stations   │
│                                                                      │
│   "the part closest      "the open-air gap        "the highest-value │
│    to a normal IT          between user and         target — often   │
│    system — easiest        satellite — where        reached THROUGH  │
│    to picture first"       most offensive-          the segments     │
│                             techniques live"         before it"      │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
   easiest to attack  →  most exploited in practice  →  highest value
```

Each segment builds on the last — a weakness in the user segment is often the way *in* to the link segment, and a foothold on the link is often the way *in* to the ground segment.

---

## 📂 File-by-file

| # | File | One-line definition | Why it's here |
|:-:|---|---|---|
| 1 | 💻 [`user-segment.md`](user-segment.md) | The terminals and user equipment that sit between a human/application and the satellite network | Closest to a normal IT system — the easiest segment to picture, and often the lowest-effort entry point for an attacker |
| 2 | 📡 [`link-segment.md`](link-segment.md) | The RF uplink/downlink channel carrying signals between ground and satellite | Builds directly on `fundamentals/communication-protocols.md` — now asking what can go wrong with that signal once it's out in the open over RF |
| 3 | 🏢 [`ground-segment.md`](ground-segment.md) | Mission control centers, ground stations, and the data-processing/networking infrastructure behind them | The highest-value target of the three — frequently reached *through* a compromised user terminal or intercepted link, not attacked directly first |

> **Where's the space segment?** The satellite itself (bus, onboard software, payload) isn't a separate file here on purpose. For this repo's specialty — offensive satellite exploitation — the space segment is less "surface to survey" and more "the target you're working toward." It's covered as a technique in [`offensive-techniques/satellite-bus-attacks.md`](../offensive-techniques/satellite-bus-attacks.md) instead.

---

## 🤔 What to look for in each file

Every note in this folder should leave you able to answer two things for that segment:

1. **What's the attack surface** — the actual components/interfaces an attacker can reach
2. **Why it matters** — what compromising it actually gets an attacker

That "why it matters" framing is what turns this into attack-surface *thinking*, not just a components list with "attacks" bolted on.

---

➡️ **Next up:** [`offensive-techniques/`](../offensive-techniques/) — same segments (plus the satellite itself), now asked *"how is this actually exploited, step by step?"*
