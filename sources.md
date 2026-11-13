# Sources

Every source this repo draws from, credited openly. Notes are written in the author's own words after reading these — never copy-pasted — but the facts, figures, and incidents referenced trace back here.

## fundamentals/why-satellite-cybersecurity.md

- ENISA, *Space Threat Landscape Report* (March 2025) — https://enisa.europa.eu/sites/default/files/2025-03/Space_Threat_Landscape_Report_fin.pdf
- Scientific American, "We Need Cybersecurity in Space to Protect Satellites" — https://www.scientificamerican.com/article/we-need-cybersecurity-in-space-to-protect-satellites/
- Aerospace Corporation, "Multi-Orbit Networks Expand the Attack Surface, But Basic Cyber Threats Remain, Experts Say" (Nov 2025) — https://news.aerospace.org/2025/11/25/multi-orbit-networks-expand-the-attack-surface-but-basic-cyber-threats-remain-experts-say/
- Dr. James Pavur, "Space Jam: Exploring Radio Frequency Attacks in Outer Space," DEF CON 30 (2022) — https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20video%20and%20slides/
- SentinelOne, "AcidRain | A Modem Wiper Rains Down on Europe" — https://www.sentinelone.com/labs/acidrain-a-modem-wiper-rains-down-on-europe/
- Just Security, "AcidRain Malware and Viasat Network Downtime in Ukraine: Assessing the Cyber War Threat" — https://www.justsecurity.org/83021/acidrain-malware-and-viasat-network-downtime-in-ukraine-assessing-the-cyber-war-threat/

## fundamentals/orbits.md

- OrbitalRadar, "Types of Orbits" — https://orbitalradar.com/types-of-orbits
- Wikipedia, "Molniya orbit" — https://en.wikipedia.org/wiki/Molniya_orbit

## fundamentals/satellite-types.md

- NewSpace Economy, "Satellite Classification Taxonomy" — https://newspaceeconomy.ca/2023/03/28/satellite-classification-taxonomy/
- Wikipedia, "CubeSat" — https://en.wikipedia.org/wiki/CubeSat

## fundamentals/hardware-components.md

- NASA, "Basics of Space Flight," Chapter 11: Spacecraft Subsystems — https://science.nasa.gov/learn/basics-of-space-flight/chapter11-1/
- NewSpace Economy, "What Are the Components of a Satellite?" — https://newspaceeconomy.ca/2023/04/05/what-are-the-components-of-a-satellite/
- Mouser Electronics, "7 Things to Know About Spacecraft Subsystems Before Your Next Trip to Mars" — https://resources.mouser.com/space/7-things-to-know-about-spacecraft-subsystems-before-your-next-trip-to-mars
- Refonte Learning, "Satellite Subsystems Explained in 2026: Power, Thermal, Propulsion, ADCS, OBC, and Payload" — https://www.refontelearning.com/blog/satellite-subsystems-explained

## fundamentals/software-components.md

- PHXCubeSat (Arizona State University), "Flight Software" — https://phxcubesat.asu.edu/subsystems/flight-software
- NASA, "cFS (core Flight System) Overview" (Richard Landau, NASA, 2024) — https://directory.elisa.tech/workshops/2024-12-Maryland/cFS-Overview-Richard-Landau-NASA.pdf

## fundamentals/communication-protocols.md

- SpaceNews, "CCSDS at 20 years" — https://spacenews.com/?p=36007
- ESA, "SpaceWire" — https://www.esa.int/Enabling_Support/Space_Engineering_Technology/Onboard_Computers_and_Data_Handling/SpaceWire
- NASA, "DTN SpaceOps Paper" (Israel D., 2021) — https://ntrs.nasa.gov/api/citations/20210013734/downloads/DTN%20SpaceOps%20Paper%202021%20Israel%20D.pdf

## fundamentals/data-formats.md

- PDS Small Bodies Node, CONTOUR mission telemetry documentation — https://pds-smallbodies.astro.umd.edu/holdings/con-cal-all-6-doc-set-v1.0/browse/hayes/common/telemetry.htm
- NASA Earthdata, "Data Processing Levels" — https://www.earthdata.nasa.gov/learn/earth-observation-data-basics/data-processing-levels

## fundamentals/ground-antennas.md

- Refonte Learning, "Satellite Antenna Design Basics in 2026: Types, Materials, and Trade-Offs" — https://www.refontelearning.com/blog/satellite-antenna-design-basics
- USU SmallSat Conference 2025, "From Dishes to Distributed Arrays: Towards Efficient and Interference-Free Satellite Ground Stations" — https://digitalcommons.usu.edu/smallsat/2025/all2025/21

## attack-surface/user-segment.md

- Help Net Security (reporting on IOActive research), "The dismal state of SATCOM security" — https://www.helpnetsecurity.com/?p=37041
- Lenders, Willbold, Bisping, "Breaking the Beam: Exploiting VSAT Satellite Modems from the Earth's Surface," DEF CON 32 (2024) — https://infocondb.org/con/def-con/def-con-32/breaking-the-beam-exploiting-vsat-satellite-modems-from-the-earths-surface

## attack-surface/link-segment.md

- Aerospace Security Project (CSIS), "Space Threat Assessment" — https://aerospace.csis.org/wp-content/uploads/2018/09/Space-System-Threats.pdf
- GPSPATRON, "Maritime GNSS Interference Worldwide: A Cumulative Analysis 2025" — https://gpspatron.com/maritime-gnss-interference-worldwide-a-cumulative-analysis-2025/

## attack-surface/ground-segment.md

- Infosecurity Magazine (Benny Czarny, OPSWAT), "Why Space Infrastructure's Biggest Cyber Risk Never Leaves the Ground" — https://www.infosecurity-magazine.com/opinions/space-cyber-risk-ground/
- UK DSIT / Actica Consulting report, via NASNI Consultants, "UK Report Warns Cloud-Linked Satellite Stations Could Lead to Cyberattacks" — https://nasniconsultants.com/?p=51070

## offensive-techniques/signal-interception.md

- Security Boulevard, "Sky-High Hack: How $600 Unlocked Global Secrets Streaming from Space" (Oct 2025) — https://securityboulevard.com/2025/10/sky-high-hack-how-600-unlocked-global-secrets-streaming-from-space/
- RTL-SDR.com, satellite interception tag/reference page — https://www.rtl-sdr.com/tag/satellite-2/

## offensive-techniques/jamming-dos.md

- CSIS, "Satellite Jamming" (On the Radar issue brief) — https://ontheradar.csis.org/issue-briefs/satellite-jamming/
- TechRadar, reporting on UT Austin/Stanford research, "A massive escalation in electronic warfare: researchers show how Russian satellites can jam GPS across Europe" (2026) — https://www.techradar.com/computing/a-massive-escalation-in-electronic-warfare-researchers-show-how-russian-satellites-can-jam-gps-across-europe-and-a-mysterious-series-of-interference-events-show-it-could-already-be-happening

## offensive-techniques/spoofing-injection.md

- IEEE Spectrum, "GPS Spoofing Attacks Are Dangerously Misleading Airliners" — https://spectrum.ieee.org/gps-spoofing-2670499105
- The Print, "What Is GPS Spoofing, Common Along India-Pakistan Border and Now Disrupting Delhi Airport" (Nov 2025) — https://theprint.in/feature/what-is-gps-spoofing-common-along-india-pakistan-border-and-now-disrupting-delhi-airport/2778509

## offensive-techniques/c2-hijacking.md

- Kratos Space, "Analysis of Thales' Successful Compromise of ESA OPS-SAT Experiment" — https://www.kratosspace.com/constellations/articles/analysis-of-thales-successful-compromise-of-esa-ops-sat-experiment
- MITRE / Aerospace Corporation SPARTA, "SV-AC-3: Compromised master keys or any encryption key" — https://sparta.aerospace.org/v2.0/related-work/threats/SV-AC-3

## Also consulted (general background)

- Romel Marin, aerospace cybersecurity and satellite security notes (PDF) — personal reference material, not quoted or copied directly
