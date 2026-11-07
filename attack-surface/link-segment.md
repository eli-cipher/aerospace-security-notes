# Link Segment

The RF uplink/downlink channel carrying signals between ground and satellite — command links that control the satellite and its sensors, and mission links that carry its operational data. Unlike the user segment (a physical device you can reach) or the ground segment (a network you can intrude on), the link is pure radio frequency, broadcast through open air. That makes it a fundamentally different kind of attack surface.

---

## What's the attack surface

- **Uplink** — the command channel to the satellite. Jamming or spoofing it means fighting for control of the satellite itself, not just disrupting a service.
- **Downlink** — the broadcast from satellite to ground/users. This is what most users and ground stations actually receive, and it's the more exposed half of the link.
- **GNSS signals specifically** — navigation links (GPS and equivalents) are a link-segment target in their own right, distinct from comms links, and currently the most heavily attacked in the real world.

## Why it matters

**Why the link is uniquely exposed:** reaching the ground segment usually requires physical access or a network intrusion. Reaching the space segment directly requires real resources — money, technical know-how, and access most attackers don't have. The link, by contrast, is just an RF signal traveling through open air — denying or deceiving it is, in the words of one threat assessment, "technologically achievable for any adversary we might face."

**Jamming** overwhelms the target signal with noise in the same radio band, so the receiver can't distinguish real data from interference:
- **Uplink jamming** targets the satellite directly — it requires detailed knowledge of the target signal and considerable transmitter power, but a successful attack can have global effects on the satellite's control.
- **Downlink jamming** targets a ground or airborne receiver instead — needs far less power, but its effects stay local (tens to hundreds of miles). This asymmetry means downlink attacks are generally easier and more reliable to pull off than uplink attacks, despite being more limited in reach.
- **"Smart" jamming** goes a step further, emulating the satellite's own signal to feed the receiver convincingly false data rather than just noise.

**Spoofing** is arguably the more dangerous of the two: instead of drowning out the real signal, the attacker captures, alters, and retransmits it — appearing to the receiving system as a trusted, authorized source. Once trusted, false commands can be inserted directly into a satellite's command receiver, potentially causing real malfunction or mission failure. It's described as one of the most discreet and deniable forms of attack on space systems, precisely because a well-executed spoof doesn't look like an attack at all — it looks like legitimate traffic.

## This isn't theoretical — it's happening at real scale right now

GNSS interference (jamming and spoofing of navigation signals specifically) has gone from occasional incident to a documented, growing pattern. In Q2 2025 alone, over 10,000 vessels were reported affected by GNSS interference — an eightfold jump from the previous quarter — spread across the Eastern Mediterranean, Red Sea, Persian Gulf, Black Sea, and Baltic Sea.

A few concrete incidents worth knowing:
- **April 2024**: falsified GNSS signals caused 117 ships to appear to simultaneously be at Beirut Airport, with 227 vessels reportedly spoofed across the Eastern Mediterranean.
- **June 2025**: over 3,000 vessels disrupted by interference in the Persian Gulf and Strait of Hormuz within less than two weeks.
- **2025, Strait of Hormuz**: a tanker collision was preceded by logged GNSS and AIS anomalies.

*(Worth noting honestly: that scale data comes from a company that sells GNSS-interference detection tools, so the numbers have some commercial incentive behind them. The underlying incidents are independently documented, but treat the precise scale figures with a little caution.)*

## What this means for an attacker (and a defender)

The link segment is where the "pure physics" argument for why satellite attacks are accessible really lands: no need to breach a network, no need to physically access hardware — just the right frequency, enough power, and in the case of spoofing, a convincing-enough signal. It's also the segment that connects the other two: a spoofed uplink command is how an attacker who's never touched a ground station or a user terminal can still reach the satellite directly.

---

**Next:** [`ground-segment.md`](ground-segment.md) — mission control and ground stations, often the destination an attacker is actually working toward.
