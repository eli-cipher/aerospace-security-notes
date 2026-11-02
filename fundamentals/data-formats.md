# Data Formats

Protocols (see [`communication-protocols.md`](communication-protocols.md)) carry the data — this is what's actually inside them. Two separate things to keep straight: how data is *packaged* for the trip, and what happens to it *after* it arrives.

---

## How data is packaged: telemetry vs. telecommand

| | Direction | Carries |
|---|---|---|
| **Telemetry** | Satellite → ground (downlink) | The satellite's own health/status data, plus payload/science data |
| **Telecommand** | Ground → satellite (uplink) | Instructions telling the satellite what to do |

Both typically travel as **CCSDS packets**, with a consistent structure:

- **Primary header** — version, packet type, an Application Process ID (identifies *what* this packet is/which component it's from), sequence count, length
- **Secondary header** — a timestamp (mission elapsed time) for when the data was captured or the command was issued
- **Payload** — the actual content, which varies by packet type: could be raw housekeeping data, a memory dump, or a subpacket stream carrying multiple smaller records (each with its own ID tagging it as status, alarm, command echo, etc.)

One detail worth knowing: commands sent up to a spacecraft are often **echoed back** down in telemetry — a confirmation subpacket showing exactly what command was received and what the result was, so ground operators aren't just assuming the uplink worked.

---

## What happens after it arrives: processing levels

Raw data straight off a satellite isn't usable science data yet — it goes through a standard pipeline (NASA's Level 0–4 model is the common reference):

| Level | What happens |
|---|---|
| **0** | Raw, reconstructed instrument data at full resolution — transmission overhead (sync frames, duplicates) stripped out |
| **1A** | Time-referenced and annotated with calibration info and georeferencing (e.g. where the satellite was) |
| **1B** | Converted into actual instrument units (not every instrument needs this step) |
| **2** | Real geophysical variables derived — e.g. actual measurements, not raw sensor counts |
| **3** | Mapped onto a consistent space-time grid — made comparable across time/location |
| **4** | Model outputs or analysis combining multiple measurements into new derived results |

A beginner-friendly way to think about it: **Level 0 is "what the sensor recorded," Level 4 is "what that data actually means."** Everything in between is progressively turning raw numbers into something a scientist (or an operator, or an attacker analyzing captured telemetry) can actually interpret.

---

**Next:** [`ground-antennas.md`](ground-antennas.md) — the hardware on the ground that actually sends and receives all of this.
