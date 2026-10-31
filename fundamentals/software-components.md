# Software Components

Hardware alone doesn't fly a satellite — software is what turns a collection of subsystems into a working spacecraft. It runs on the onboard computer (see [`hardware-components.md`](hardware-components.md)) and is the layer that actually reads sensors, issues commands, and decides what happens next.

---

### 🧠 Flight Software (FSW)

The core software running on the OBC — often called the "brain" of the satellite. It handles every operation needed for the mission: talking to hardware subsystems, scheduling and executing commands, collecting housekeeping data, and keeping the spacecraft alive and functioning.

**How it actually talks to hardware** (using a real cubesat as an example):
- **ADCS**: a driver converts high-level commands into something the attitude-control hardware understands, and parses incoming attitude telemetry only when needed (ADCS can report status many times a second — far more than the OBC needs to process continuously).
- **Power (EPS)**: FSW doesn't do the actual power management — the power subsystem handles that itself. FSW just sends commands and checks that power rails switched on/off correctly by confirming expected voltage.
- **Payload**: a manager relays operation commands to the payload's driver (e.g. a camera), which executes the action and hands data back (e.g. an image, plus sensor status like temperature).
- **Comms**: a manager processes incoming communication events, passes received data to command handling, and sends regular "heartbeat" signals so ground knows the satellite is alive.

### ⏱️ Command Scheduling & Execution

Commands are usually read from a schedule file and executed at their assigned time — but FSW also supports immediate execution for emergencies, bypassing the normal schedule when something needs to happen *now*.

### 📥📤 Telemetry, Uplink & Downlink Handling

- **Uplink**: commands arrive via the comms subsystem and get handed off to a command-ingest process.
- **Telemetry**: a dedicated process periodically pulls data from each hardware-control component and logs it.
- **Downlink**: that logged telemetry gets transmitted to ground and reviewed by the mission operations team — including logged events like failed commands, which operators use to catch problems.

---

## The shift toward shared frameworks

Flight software used to be built bespoke, mission by mission. That's changing — the field is converging on reusable, open frameworks instead of each team reinventing the same core logic.

**NASA's core Flight System (cFS)** is the clearest example:
- **Architecture**: a *core* (the Flight Executive) provides services every mission needs — starting/stopping apps, logging and downlinking events, passing messages between apps via publish/subscribe, managing configuration and time. On top of that sit modular, swappable *apps* for mission-specific needs (hardware interfaces, data processing).
- **Portable by design**: a platform abstraction layer lets the same software run across different operating systems and processors — built-in support for RTEMS, VxWorks, and even desktop Linux for testing.
- **Why it matters**: reuse means fewer defects, lower cost (NASA cites at least 50% savings over building software from scratch each time), and more predictable schedules.
- **How widely adopted it already is**: in 2020, cFS became the standard flight software framework across NASA, ESA, CSA, and JAXA. It's running on 40+ NASA missions (including the Gateway station and the Roman Space Telescope), plus commercial missions — notably Intuitive Machines' Odysseus lunar lander, which used cFS's flexibility to quickly reprogram its landing LiDAR configuration.

**Why this matters for this repo specifically**: shared, reusable software frameworks are a double-edged sword from a security standpoint. A vulnerability discovered in a widely-used framework like cFS doesn't just affect one satellite — it's potentially relevant across dozens of missions and multiple space agencies running the same core code.

---

**Next:** [`communication-protocols.md`](communication-protocols.md) — how this software actually talks to the ground: the protocols carrying commands up and telemetry down.
