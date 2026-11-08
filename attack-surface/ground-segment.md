# Ground Segment

Mission control centers, ground stations, and the data-processing/networking infrastructure behind them. This is the highest-value target of the three segments in this folder — and frequently the one actually reached *through* a compromised user terminal or intercepted link, not attacked head-on first.

---

## What's the attack surface

- **Enterprise network infrastructure** — ground segments have the same entry points as any ordinary corporate network: logins, email, remote access, internal systems.
- **Supply chain** — hardware and software passing through long, international manufacturing and integration chains, with limited visibility into every hand it passes through.
- **Software update pipelines** — once a satellite is in orbit, the update channel is one of the few remaining ways to get new code onto it — which makes it a prime target if that channel isn't properly secured.
- **Cloud-linked ground stations** — a growing architecture (Ground-Station-as-a-Service) where commands and downlinked data pass through cloud infrastructure instead of staying on a closed, dedicated network.
- **People** — insiders and careless employees, alongside the more commonly discussed state-nexus groups, criminals, and hacktivists.

## Why it matters

**Why attackers go for the ground first:** a satellite is hard to reach once it's in orbit — no walking up to patch it, no physical access, no easy do-overs. The ground segment has none of those protections; it looks and behaves like any other IT network, which makes it the much more practical target. One assessment put it bluntly: a single compromised login can take down a critical satellite network within minutes.

**Supply chain is the most emphasized risk.** ENISA has flagged hardware tampering as a real concern anywhere along long, international manufacturing chains — including a documented scenario involving a USB drive plugged into a satellite during assembly or transit, well before the satellite ever reaches orbit. A UK Space Agency-commissioned report separately rates supply-chain compromise among the most likely threats facing the sector.

**Software updates are the main remaining route for malware post-launch.** Once a satellite is operational, the update pipeline — the mechanism meant to fix and improve the system — is also one of the few channels still open for an attacker to get new, malicious code aboard. This is exactly the path the Viasat KA-SAT attack took: attackers compromised the update infrastructure and pushed a wiper malware (AcidRain) down to ground terminals. Worth noting specifically for this file: that entire attack happened through the ground segment — the space segment itself was never touched.

**The attack surface is actively growing, not shrinking.** A UK government-commissioned report (DSIT, conducted by Actica Consulting) warns that linking ground stations to cloud services — increasingly common as "Ground-Station-as-a-Service" offerings like AWS Ground Station spread — widens the attack surface by adding new interfaces and dependencies. The report treats the potential consequences as more serious than a typical IT breach: stolen satellite data, disrupted services, and even physical consequences like moving a satellite out of position or disabling its payload entirely. It specifically flags timing attacks and command injection as especially dangerous during launches and other time-sensitive operations. As of the report, the UK has no regulatory framework for ground station infrastructure at all.

## What this means for an attacker (and a defender)

The ground segment is where theory becomes practice for a full takeover chain: the user and link segments get an attacker *toward* the satellite, but the ground segment — mission control, the command pipeline, the update channel — is usually where real operational control actually lives. It's also the segment least protected by physics or distance; everything here is reachable the same way any enterprise network is reachable, which is exactly why Viasat, the most consequential satellite cyberattack to date, never needed to touch a satellite at all.

---

That completes the attack-surface map: user segment (the easiest entry point) → link segment (the open-air gap in between) → ground segment (the highest-value target, often reached through the other two).

**Next:** [`offensive-techniques/`](../offensive-techniques/) — same segments (plus the satellite itself), now asked *how is this actually exploited, step by step?*
