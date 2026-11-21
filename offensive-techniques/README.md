# ⚔️ offensive-techniques/

This is the deep end — and the author's specialty. Where [`attack-surface/`](../attack-surface/) mapped *where* a satellite system can be touched, this folder covers *how* each touch-point actually gets exploited, and how those techniques **chain together** into full command-and-control of a satellite.

> ⚠️ **Scope note:** this folder documents real attack methodology to help you understand how satellite systems actually get broken — it is not a how-to for unauthorized access. Use only against systems you own or are explicitly authorized to test.

## 🔗 The full attack chain

```
┌───────────────────────────────────────────────────────────────────────────┐
│                     🛰️  FROM LISTENING TO FULL TAKEOVER                     │
└───────────────────────────────────────────────────────────────────────────┘

  👂 1. signal-interception.md
       "see what's there — passively, with ~$600 of gear"
              │
              ▼
  📵 2. jamming-dos.md
       "deny it to everyone, cheaply, with no need to understand it"
              │
              ▼
  🎭 3. spoofing-injection.md
       "don't drown the signal — replace it with a convincing lie"
              │
              ▼
  🔑 4. c2-hijacking.md
       "aim that lie at the command interface — first real takeover milestone"
              │
              ▼
  ⚙️ 5. satellite-bus-attacks.md
       "go past the command interface — reach every subsystem on the bus"
              │
         ┌────┴────┐
         ▼         ▼
🌐 6. vsat-      🔁 7. replay-telemetry-
   network-         tampering.md
   attacks.md       "stay hidden once
   "the ground        you're in"
    network
    behind it all"
```

## 📂 File-by-file

| # | File | Core idea in one line |
|---|---|---|
| 1 | [`signal-interception.md`](signal-interception.md) | Passively capture satellite signals with consumer SDR gear — no network access needed, and roughly half of GEO links are unencrypted. |
| 2 | [`jamming-dos.md`](jamming-dos.md) | Overpower a legitimate signal with RF noise on the same frequency — cheap, reversible, and the simplest active attack here. |
| 3 | [`spoofing-injection.md`](spoofing-injection.md) | Replace a real signal with a convincing fake one — the receiver keeps working, it's just been fed a lie. |
| 4 | [`c2-hijacking.md`](c2-hijacking.md) | Steal or replace command keys so the satellite executes an attacker's commands as if they came from the real operator. |
| 5 | [`satellite-bus-attacks.md`](satellite-bus-attacks.md) | Once inside, reach the unauthenticated internal bus — turning one compromised app into full spacecraft compromise. |
| 6 | [`vsat-network-attacks.md`](vsat-network-attacks.md) | Zoom out to the ground network managing many terminals at once — design-level flaws, not just one bad modem. |
| 7 | [`replay-telemetry-tampering.md`](replay-telemetry-tampering.md) | Replay real signals and falsify telemetry so operators keep seeing "all normal" while the system is actually compromised. |

## 📖 Why this order

The first four files (1–4) follow one straight line: **see it → deny it → deceive it → control it.** Each is a prerequisite for the next. From file 5 onward, the chain branches into *what you do with control* — going deeper into the spacecraft itself (5), stepping back out to the ground network that manages the whole fleet (6), and finally, staying undetected once you're in (7).

## ⏭️ What's next

This is the last folder in the repo's reading order. Once you've been through all seven files here, you've covered the full path from "I can see a satellite's signal" to "I can take it over and stay hidden while doing it."

---

⬅️ [Back to repo root](../README.md)
