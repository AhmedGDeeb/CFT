# Value Proposition

**Venture:** SentinelMesh — Monitoring without infrastructure.

**Session:** 2 — Customer discovery and value proposition

**Date:** 11 November 2026

**Author:** Ahmad Deeb

**Status:** Draft v1 — to be validated through customer interviews

---

## 1. Executive summary

SentinelMesh provides forest protection agencies and environmental authorities in Syria with a solar-powered, self-healing IoT mesh network that detects wildfires early and relays alerts without relying on the country's damaged communication and power infrastructure.

The value proposition is not the sensor network itself. It is the **time between ignition and detection** — the window in which a fire can still be contained. Syria's forest fire response is constrained by difficult terrain, water shortages, unexploded ordnance, and communication gaps in exactly the areas where fires start. SentinelMesh closes the detection gap with an independent network that works where cellular coverage and grid power do not.

---

## 2. Customer and problem

**Primary customer segment:** Forest protection and environmental agencies operating in Syria — specifically the Ministry of Emergency and Disaster Management, the General Organization for Remote Sensing's Forest and Fire Monitoring Platform, and civil defence units responsible for forest fire response.

**Secondary customers:** Agricultural cooperatives and farmers adjacent to forest areas; ecological researchers and universities.

**Problem statement:**
Syria's forests are burning at an accelerating rate, and the agencies responsible for protecting them lack continuous, field-level monitoring in the areas most at risk.

The evidence is stark:

- **2,367 fire incidents** were recorded in the first quarter of 2026 alone, up from 2,261 in the same period of 2025.
- Syria lost **12,000 hectares** of natural forest in 2025, equivalent to **2.0 Mt of CO₂ emissions**. Between 2001 and 2025, the country lost **40% of its 2000 tree cover** — and wildfire was the single largest driver of that loss.
- Firefighting teams face "difficult terrain, smoke exposure, water shortages and other hazards in some forest areas," and the Ministry has acknowledged that some proposed solutions "require infrastructure not available in a country exhausted by fourteen years of war".
- The government is actively developing its first national early-warning system for forest protection, and has participated in regional workshops on wildfire preparedness — signalling institutional demand for exactly this capability.
- UNDP Syria itself issued a tender for an "Integrated Early Detection and Response System for Forest Wildfires" in November 2025, confirming that the buyer is actively procuring this solution.

**Why existing alternatives fall short:**

| Alternative | Limitation |
|---|---|
| Satellite fire alerts (VIIRS, MODIS) | Detection latency; coarse resolution; cannot distinguish small ground fires under canopy |
| Citizen reporting (phone calls) | Depends on someone being present and having coverage; slow and unreliable |
| Government monitoring platform | Centralised, dependent on remote sensing and weather data, not field-level |
| Commercial IoT sensor networks | Require connectivity and grid power; not designed for war-damaged infrastructure |
| Manual patrols | Limited coverage, dangerous terrain, unexploded ordnance risk |

---

## 3. Value proposition statement

**Primary statement:**

> For Syrian forest protection agencies that lose forest to fires detected too late, SentinelMesh provides a solar-powered, self-healing mesh network that detects smoke and fire at the field level and relays alerts without any dependence on cellular coverage or grid electricity — so fires are caught while they can still be contained, in the remote areas where detection currently fails.

**Structured form:**

- **For** forest protection agencies and environmental authorities in Syria
- **Who** lose forest cover to fires that are detected too late, in areas with no reliable connectivity or power
- **SentinelMesh is** a decentralised, solar-powered IoT mesh network with edge AI fire detection
- **That** detects smoke and fire at the field level and relays alerts through a self-healing network to a central dashboard
- **Unlike** satellite alerts, citizen reporting, or connectivity-dependent sensor systems
- **SentinelMesh** operates independently of damaged infrastructure, extends coverage by adding nodes, and continues functioning when individual nodes fail

---

## 4. Value delivered, by beneficiary

**For the forest protection agency:**
- Earlier detection of fires in remote areas, extending the containment window
- Continuous monitoring where patrols cannot reach or are unsafe
- Real-time alerts and a historical record of fire risk conditions
- An independent network that functions during infrastructure outages
- A low-cost, modular system that scales by adding nodes

**For the civil defence responder:**
- Alert with location, so response is dispatched to the right place faster
- Sensor context (temperature, humidity, wind proxy via solar irradiance) to inform response
- Reduced exposure to detecting fires by chance or by citizen report

**For the climate:**
- Reduced hectares burned per fire event
- Reduced CO₂ emissions from avoided forest loss — Syria's 2025 forest loss alone represented 2.0 Mt CO₂
- Protection of a rare and degraded forest estate, including species of conservation concern such as the Cilician fir (*Abies cilicica*), which persists in Syria in small, degraded coastal remnants in urgent need of protection

---

## 5. How the value proposition has changed

This section records the evolution of the value proposition, as required for the evidence log.

| Version | Statement | What changed and why |
|---|---|---|
| v0 — Pivot to SentinelMesh | "A decentralised, solar-powered IoT mesh network for independent environmental monitoring in remote Syria — fire, wildlife, herd and weather." | Broadened from irrigation to multi-use environmental monitoring. Added camera/edge AI, two-tier node architecture, and the war-damaged-infrastructure framing. |
| v1 — Session 2 (current) | "A solar-powered, self-healing mesh network that detects smoke and fire at field level and relays alerts without connectivity or grid power — so Syrian forest agencies catch fires while they can still be contained." | Narrowed from multi-use to **one lead problem**: wildfire early detection. Named the primary customer explicitly (forest protection agencies). Added the procurement signal (UNDP tender) and the quantified forest-loss evidence. Multi-use cases retained as expansion, not as the pitch. |

**Key insight driving the change:** a multi-use platform is technically accurate but commercially unfocused. The programme's Session 1 output is a *problem-and-customer page* — singular. The evidence points to one urgent, funded, institutionally-owned problem: **wildfire detection for Syrian forest agencies**. Irrigation, wildlife tracking and herd counting remain valid applications of the same platform and are listed as expansion, but the value proposition leads with fire.

---

## 6. Expansion of project scope

The following expansions are recorded so they can be tested and, where necessary, descoped.

### 6.1 From monitoring to early detection
**Original scope:** collect and transmit environmental data.
**Expanded scope:** run lightweight YOLO models on-device to detect smoke and fire in captured images, converting raw data into an **alert**. The product is an alert that triggers response, not a dashboard.

### 6.2 From connected sensors to a connectivity-independent mesh
**Original scope:** sensor nodes reporting to a server.
**Expanded scope:** a self-organising mesh in which nodes relay data peer-to-peer, functioning with no cellular or internet coverage at field level. Coverage extends by adding nodes; the network self-heals when a node fails.

### 6.3 From field-only to field-plus-backbone architecture
**Original scope:** field deployment only.
**Expanded scope:** a gateway node at the backbone optionally connects to the internet for dashboard access and historical analytics — while the field network continues to operate fully offline if that connection is lost.

### 6.4 From grid-dependent to zero-emission, off-grid operation
**Original scope:** powered nodes.
**Expanded scope:** solar-powered nodes with battery backup, giving zero-emission operation and removing dependence on grid electricity — a practical necessity given Syria's damaged power infrastructure and a climate attribute in its own right.

### 6.5 From single-use to multi-use platform (secondary)
**Original scope:** fire detection only.
**Expanded scope:** the same node architecture supports soil moisture, weather, wildlife and herd monitoring. These are **expansion use cases**, to be validated only after the fire-detection MVP is proven.

### 6.6 From hardware to hardware-plus-dashboard
**Original scope:** a device.
**Expanded scope:** a device plus a dashboard providing real-time alerts, sensor readings and historical trends. Business model implications addressed in Sessions 7–8.

**Scope discipline:** expansions 6.1–6.4 are core to the value proposition and will be tested in the MVP. Expansions 6.5–6.6 are secondary and will be validated before commitment.

---

## 7. Assumptions to validate

| # | Assumption | How it will be tested |
|---|---|---|
| A1 | Fires in target areas are currently detected too late for effective containment | Interviews: "Walk me through the last fire you responded to — how was it detected, and how long before response?" |
| A2 | Target forest areas lack reliable cellular coverage and grid power | Interviews with rangers/agency staff; site assessment during MVP |
| A3 | Forest agencies have budget or donor funding to procure monitoring systems | Interviews; UNDP tender evidence; donor project landscape (FAO/ECHO early warning project) |
| A4 | A low-cost mesh node ($50–110) is affordable at deployment scale | Cost modelling in Session 8; agency budget questions |
| A5 | Smoke/fire detection via ESP32-CAM + YOLO is accurate enough to generate actionable alerts | MVP test: controlled smoke test; false-positive assessment |
| A6 | Agencies will act on an automated alert from an unfamiliar system | Interviews: "What would you need to see to trust an automated alert?" |
| A7 | The mesh range (~1.2 km LOS, ~400 m NLOS) is sufficient for target terrain | MVP test: field range measurement in representative terrain |

---

## 8. Evidence status

| Item | Status |
|---|---|
| Customer interviews completed | [number — update as interviews are conducted] |
| Interviews scheduled | [number] |
| Evidence log | Maintained at `customer-evidence/evidence-log.md` |
| MVP test plan | In development — Session 3 output (13 Nov) |
| Documented procurement signal | UNDP Syria tender: "Provision of Integrated Early Detection and Response System for Forest Wildfires," Nov 2025 |
| Documented policy signal | Syria developing first national forest early-warning system; regional workshop participation |

*This section will be updated as interview evidence is collected. The value proposition will be revised if evidence contradicts any assumption in Section 7.*

---

## 9. One-sentence version

> SentinelMesh gives Syrian forest protection agencies a solar-powered, self-healing mesh network that detects fires at field level and relays alerts without connectivity or grid power — so fires are caught while they can still be contained, in the remote areas where detection currently fails.

---
