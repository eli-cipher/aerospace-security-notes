# 💀 offensive-techniques/

Don't start here. This folder assumes [`fundamentals/`](../fundamentals/) and [`attack-surface/`](../attack-surface/) — every technique below is a concrete, step-by-step version of an attack vector already named and reasoned-through in `attack-surface/`.

This is the deepest section in the repo, and the specialty this whole project builds toward: chaining vulnerabilities end-to-end — ground segment → command link → onboard software — toward full command-and-control takeover of a satellite.

---

## 🧭 The Flow

```
┌───────────────────────────────────────────────────────────────────────────┐
│                                                                           │
│  1. SIGNAL        2. JAMMING       3. SPOOFING /      4. C2               │
│  INTERCEPTION  →  / DoS        →   INJECTION     →    HIJACKING           │
│  observe, don't   deny service      fake or inject     hijack the         │
│  touch yet         (no content      real content        command interface │
│                     needed)                                               │
│                                                                   │       │
│      ┌────────────────────────────────────────────────────────────┘       │
│      ▼                                                                    │
│  5. SATELLITE      6. VSAT NETWORK      7. REPLAY / TELEMETRY             │
│  BUS ATTACKS   →   ATTACKS          →   TAMPERING                         │
│  what's behind      a parallel,          close the loop — mask            │
│  the hijacked        network-centric      the takeover so it              │
│  interface           path to the          sticks                          │
│                       same targets                                        │
│                                                                           │
└───────────────────────────────────────────────────────────────────────────┘
   passive  →  active, no payload  →  active, fake payload  →  control  →  persistence
```

Roughly follows the attacker's own path from *observe* to *control* to *stay in control*.

---

## 📂 File-by-file

| # | File | Goal | Why it's here |
|:-:|---|---|---|
| 1 | 👁️ [`signal-interception.md`](signal-interception.md) | Passively capture satellite signals to gather intelligence | Lowest-risk, lowest-footprint start — and a prerequisite for almost everything after it, since you need to see the traffic before faking, replaying, or hijacking it |
| 2 | 📵 [`jamming-dos.md`](jamming-dos.md) | Deny service by overwhelming the signal | The simplest *active* attack — no need to understand the signal's content, just its presence |
| 3 | 🎭 [`spoofing-injection.md`](spoofing-injection.md) | Impersonate a legitimate signal to inject false data or commands | Now content matters — builds directly on what interception taught about signal structure |
| 4 | 🕹️ [`c2-hijacking.md`](c2-hijacking.md) | Spoofing aimed specifically at the satellite's command-and-control interface | The chain's first real "takeover" milestone — the ability to issue commands, not just inject noise |
| 5 | 🛰️ [`satellite-bus-attacks.md`](satellite-bus-attacks.md) | Exploit what's actually sitting behind the hijacked command interface — the onboard bus (CAN/I2C/SPI), firmware, the device itself | This is the "space segment" attack surface that `attack-surface/` deliberately left for this file |
| 6 | 🌐 [`vsat-network-attacks.md`](vsat-network-attacks.md) | A parallel, network-centric path into the ground/link segments via VSAT terminals and insecure network protocols | Placed after the RF chain so you can compare the two approaches to reaching the same targets |
| 7 | 🔁 [`replay-telemetry-tampering.md`](replay-telemetry-tampering.md) | Replay or tamper with telemetry/telecommand data to mask an ongoing takeover | Closes the loop — once you can intercept (1) and inject (3), this is what makes the takeover *sustainable* rather than a one-shot disruption |

---

## 🤔 What to look for in each file

Every note here should give you three things:

1. **Goal** — what the attacker is actually trying to achieve
2. **Technique / methodology** — how it's actually done, step by step
3. **Why this matters for the end-to-end takeover chain** — what this step hands you going into the next file

This folder is the practical payoff of the whole repo: `fundamentals/` gave you the vocabulary, `attack-surface/` gave you the map, this gives you the route.

---

⚠️ **Scope reminder:** this is attack methodology for understanding how satellite systems actually get broken — not a how-to for unauthorized access. Use only against systems you own or are authorized to test.
