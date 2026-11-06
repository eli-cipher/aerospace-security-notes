# User Segment

The terminals and user equipment that sit between a human (or an application) and the satellite network — modems, VSAT terminals, handheld satcom devices, and the hardware/software running on them. This is the segment closest to a normal IT system, which is exactly why it's the easiest attack surface to picture first.

---

## What's the attack surface

- **Firmware** — the software running on the modem/terminal itself. If it accepts updates without verifying who sent them, anyone who can reach the device can potentially replace its firmware entirely.
- **The device's own OS/software stack** — terminals are small embedded computers, often running old, unpatched Linux kernels or custom stacks that haven't seen a real security review.
- **The RF interface to the dish** — the assumption that "only the satellite can talk to this terminal" turns out to be false in practice; a terminal's antenna has side lobes (weaker signal paths off the main beam) that can still receive a ground-based transmission.
- **Authentication (or the lack of it)** — hardcoded credentials and undocumented backdoors, baked into firmware at the factory, are a real and recurring finding across this class of device.

## Why it matters

Two real pieces of research make this concrete, not theoretical:

**IOActive's SATCOM terminal research** found backdoors, hardcoded credentials, undocumented/insecure protocols, and weak encryption across firmware from the most widely-deployed Inmarsat and Iridium ground terminals — the kind of equipment used across maritime, aerospace, emergency services, energy, military, and media sectors. In some cases, compromise required no user action at all: a single specially-crafted message sent from one ship to another was enough to reach an affected system remotely.

**DEF CON 32's "Breaking the Beam"** (Lenders, Willbold, Bisping) went further and demonstrated a full, working attack chain against a real, widely-deployed VSAT modem (the Newtec MDM2200):

1. Reverse-engineered the modem's firmware and network stack
2. Found no source authentication on firmware updates, plus an outdated, long-unpatched Linux kernel (2.6.35) underneath
3. Using roughly $2,000 of software-defined radio equipment, transmitted a signal from the ground directly into the terminal's dish — not through the satellite at all, but through the dish's *side lobe*, a weaker off-axis reception path nobody had assumed was reachable from Earth
4. Pushed a bogus firmware update through that opening, and obtained a full remote root shell on the modem

The researchers estimate that 10-20% of the few million VSAT modems deployed worldwide use the vulnerable protocol family this attack targets — this isn't a one-off device, it's a meaningful slice of equipment actually in service for maritime, aerospace, media broadcasting, and other critical terrestrial users who often have no alternative communications.

## What this means for an attacker (and a defender)

The user segment breaks a quiet assumption baked into a lot of satellite system design: that a dish's directionality is itself a security boundary — if you're not in line with the satellite, you can't reach the terminal. "Breaking the Beam" shows that assumption is false; the side lobe is a real, exploitable path, reachable with consumer-grade hardware and no access to the operator's network, the satellite, or even the main beam. Combined with the kind of firmware weaknesses IOActive found — hardcoded credentials, unauthenticated updates, ancient unpatched kernels — the user segment is often the *lowest-effort* entry point into a satellite system, not the hardest: no need to compromise a ground station or spoof a satellite link when the terminal sitting on a customer's roof will hand over root access on its own.

---

**Next:** [`link-segment.md`](link-segment.md) — the RF uplink/downlink in between, where these terminals and the satellite actually meet.
