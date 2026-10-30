# Hardware Components

Whatever a satellite's mission, it's built from the same core set of physical subsystems. Eight cover the full picture — not every satellite needs every one (an atmospheric probe may skip propulsion entirely), but this is the standard set.

---

### 🏗️ Structure & Mechanisms

The physical skeleton — holds everything together, survives launch loads, and provides mounting points, grounding, and radiator surfaces. Includes deployables: solar array hinges, antenna booms, release mechanisms.

### 🔋 Electrical Power System (EPS)

Generates, stores, regulates, and distributes power. Solar arrays generate it, batteries (commonly lithium-ion) store it, a power conditioning and distribution unit (PCDU) regulates and routes it to everything else.

### 🌡️ Thermal Control System (TCS)

Keeps every component inside its operating temperature range using insulation, radiators, heaters, and heat pipes — space swings between extreme heat (sunlit side) and extreme cold (shadow) with no air to moderate it.

### 🧭 Attitude Determination & Control (ADCS)

Figures out which way the satellite is pointing and corrects it — so antennas, sensors, and solar panels stay aimed correctly. Determination side: star trackers, sun sensors, magnetometers, gyros. Control side: reaction wheels, magnetorquers, or thrusters.

### 🚀 Propulsion

Provides the delta-v (velocity change) for orbit insertion, station-keeping, and maneuvers, plus thruster-based attitude correction when ADCS alone isn't enough.

### 🧠 Onboard Computer / Command & Data Handling (OBC / C&DH)

The satellite's central computer — runs flight software, sequences commands, handles fault detection/recovery, and manages onboard data storage.

### 📡 Telemetry, Tracking & Command (TT&C)

The hardware link back to Earth: low-rate command uplink, telemetry downlink (health/status data), and often a separate high-rate downlink for payload data.

### 🎯 Payload

The instruments that justify the whole mission — everything above exists to keep this working. What it is depends entirely on the satellite's purpose (see [`satellite-types.md`](satellite-types.md)): transponders/antennas for comms, cameras/sensors for Earth observation, GPS receivers/atomic clocks for navigation, telescopes/spectrometers for science.

---

## What's changing (current trends)

- **Higher-efficiency solar cells** — triple-junction GaAs cells now reach 30–32% efficiency at beginning of life.
- **COTS components are mainstream** — screened commercial battery cells and ARM-based processors are now common even outside cubesats, not just in low-cost platforms. This is directly relevant to this repo's security angle: commercial-off-the-shelf parts inherit whatever weaknesses they came with.
- **Electric propulsion as the default** — now standard for GEO station-keeping and large constellations, with krypton/iodine replacing costlier propellants.
- **Green propellants replacing hydrazine** — safer alternatives like AF-M315E are displacing older toxic chemical propellants.
- **Open flight software** — NASA's cFS (core Flight System) is a widely adopted open architecture layer rather than every mission building bespoke software from scratch.
- **Higher-rate links** — Ka-band now supports multi-Gbps downlinks, and optical laser terminals are moving from experimental to operational.
- **Onboard processing power is increasing** — radiation-hardened FPGAs now handle real payload data processing in orbit, not just on the ground after downlink.

---

**Next:** [`software-components.md`](software-components.md) — the flight software and onboard systems that actually run this hardware.
