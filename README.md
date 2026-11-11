# SentinelMesh: 
> Solution Description, Cost, and Coverage

<p align="center">
  <img src="assets/logo/sentinelmesh-logo.svg" alt="SentinelMesh logo" width="360">
</p>


Personal documentation repository for my participation in the **Climate Founders Track**, the climate tech edition of UNDP ICPSD's Virtual Digital Business Pre-Incubation (VDBI) programme.

**Participant:** Ahmad Deeb
**Venture:** SentinelMesh — a solar-powered, self-healing IoT mesh for independent environmental monitoring in remote Syria
**Programme dates:** Fri 6 Nov – Wed 16 Dec 2026
**Status:** 🟡 In progress — problem and solution defined, customer discovery underway

---

## 1. About the Programme

The Climate Founders Track is a seven-week, fully online pre-incubation programme run by the **United Nations Development Programme — Istanbul International Center for Private Sector in Development (UNDP ICPSD)**.

Over seven weeks, participants take a climate idea or early venture from a clear problem and first customer to an evidence-based pitch. Every session adds one section to a venture workbook, so participants finish with:

- a complete **venture workbook**
- a **pitch deck** (8–10 slides)
- a **90-day action plan**

### Who is supporting it

| Role | Name / Organisation |
|---|---|
| Programme owner | UNDP ICPSD (Istanbul International Center for Private Sector in Development) |
| Programme coordination | Halit Duran, PhD — Entrepreneurship Research and Partnerships Analyst, UNDP ICPSD |
| Lead Trainer | Mohammed Abdelaziz |
| Trainer | Afonso Zinga |
| Guest contributors | Climate and investment specialists (masterclasses from Week 2); jury of mentors, incubator managers and climate specialists at Demo Day |
| Optional learning partner | HP LIFE (free self-paced courses, own certificates) |

### Programme format

- **12 live sessions** of 2 hours, Wednesdays and Fridays, 15:00–17:00 Istanbul time (UTC+3). Session 12 is on Monday 14 December.
- **Weekly outputs**, each becoming a section of the venture workbook.
- **Three individual 60-minute mentoring sessions** per venture (Rounds: 9–13 Nov, 23–27 Nov, 7–11 Dec).
- **Guest masterclasses** from Week 2.
- **Demo Day** on Wed 16 Dec 2026: 4-minute pitch + 3 minutes of jury Q&A.

### Certificate requirements

Issued after Demo Day only if **all three** are met:

- [ ] Attend at least **8 of 12** live sessions (recordings do not count)
- [ ] Submit **all weekly outputs** + final workbook, pitch deck and 90-day action plan by **Tue 15 Dec**
- [ ] Complete at least **2 of 3** mentoring sessions

---

## 2. My Venture: SentinelMesh

**Tagline:** [suggested: *Monitoring without infrastructure.*]

### The climate problem

Remote areas of Syria face a compounding environmental risk: wildfires and drought are increasing, while the country's communication and power infrastructure remains severely damaged. Forest rangers, farmers and researchers have no reliable way to monitor fire risk, soil and weather conditions, or wildlife and livestock in areas where cellular coverage and grid electricity cannot be assumed. Early warning is the difference between a contained incident and a lost forest or harvest — but the monitoring systems that provide it depend on exactly the infrastructure that is missing.

### The solution

SentinelMesh is a **decentralised, solar-powered IoT mesh network** that provides independent, real-time environmental monitoring for remote areas. It combines low-cost **ESP32 microcontrollers**, **solar power**, and **edge AI** to create a self-sustaining network that operates without relying on government infrastructure or constant electricity.

The system consists of two node types:

| Node type | Role | Components |
|---|---|---|
| **Edge Node** | Data collection and AI processing | ESP32-CAM, environmental sensors (temperature, humidity, soil moisture, solar irradiance), solar panel, battery |
| **Backbone Node** | Mesh routing and data relay | ESP32, solar panel, battery, long-range antenna |

Edge nodes capture images and sensor readings, run lightweight AI models locally, and transmit alerts and data through the mesh to a central dashboard. The mesh topology ensures that if one node fails or loses connection, data still reaches its destination through alternative paths.

### How it works

**1. Data collection.** Edge nodes are deployed in forests, farms or remote areas. Each is equipped with an ESP32-CAM for image capture, a DHT22 temperature/humidity sensor, a soil moisture sensor, and a solar irradiance sensor. Data is collected at regular intervals (e.g. every 5 minutes); images are captured periodically (e.g. every 30 minutes) or triggered by motion or anomaly detection.

**2. Edge AI processing.** Lightweight YOLO models (e.g. YOLOv8n or TinyYOLO) run directly on the ESP32 or a companion edge device. The model performs wildfire detection (smoke or fire in captured images), wildlife monitoring (detection and classification) and herd counting. Only metadata (detection results, sensor readings) and thumbnail images are transmitted, reducing bandwidth and power consumption.

**3. Mesh networking.** Nodes communicate using ESP-MESH or LoRa mesh protocols. Each node can act as a repeater, forwarding data from other nodes. The mesh is self-healing: if a node fails, data automatically routes through alternative paths. The network is independent of cellular or Wi-Fi infrastructure, making it suitable for remote areas.

**4. Data transmission and dashboard.** Data is relayed through the mesh to a Gateway Node connected to the internet via satellite or a local server. The gateway uploads to a cloud dashboard providing real-time sensor readings, fire and anomaly alerts, historical trends, and wildlife and herd tracking logs.

**5. Power management.** Each node is powered by a solar panel and LiFePO4 battery with a charge controller. ESP32 deep sleep between readings, edge AI models optimised for efficiency, and a mesh protocol that minimises transmission power ensure continuous operation during outages or in off-grid locations.

### MVP use cases

- **Hyper-local weather and soil monitoring** — real-time data for farmers and researchers
- **Wildfire early warning** — smoke and fire detection via edge AI
- **Automated wildlife tracking** — species identification and logging for ecological research
- **Herd counting** — livestock monitoring for farmers

### Primary customer for the pitch

[To be confirmed — recommend: **forest rangers and environmental agencies**, with wildfire early warning as the lead problem. Secondary users: farmers and agricultural cooperatives, researchers and universities.]

### Users, needs and value

| User group | Primary need | SentinelMesh value |
|---|---|---|
| Forest rangers & environmental agencies | Early fire detection | Real-time alerts via mesh network |
| Farmers & agricultural cooperatives | Yield and herd management | Direct economic impact through improved data |
| Researchers & universities | Validation and field data | Early adopters who validate the technology and provide feedback |

### Why this matters for Syria

- **War-affected infrastructure:** Syria's communication and power networks are severely damaged; SentinelMesh provides an independent solution.
- **Climate threats:** wildfires and droughts are increasing; early warning systems save lives and livelihoods.
- **Agricultural support:** farmers need real-time data to make informed decisions.
- **Low cost, high impact:** a single node costs roughly $50, making it accessible for NGOs, researchers and communities.

---

## 3. Technical Stack

| Component | Technology |
|---|---|
| Microcontroller | ESP32 / ESP32-CAM |
| Mesh protocol | ESP-MESH (or LoRa mesh for longer range) |
| AI framework | TensorFlow Lite for Microcontrollers (YOLOv8n / TinyYOLO) |
| Sensors | DHT22, soil moisture, LDR, MQ-2 (smoke) |
| Power | Solar panel (5–10 W), LiFePO4 battery, charge controller |
| Dashboard | Web app (Flask/Django) or Power BI |
| Data storage | Local SQLite / Cloud (Firebase, AWS IoT) |

---

## 4. Cost and Coverage

### Approximate device costs

| Node type | Core components | Approximate cost (USD) |
|---|---|---|
| **Edge Node** (camera + sensors) | ESP32-CAM, DHT22, soil moisture sensor, LDR, solar panel (5 W), 18650 battery, TP4056 charger, weatherproof enclosure, antenna module | $80 – $110 |
| **Backbone Node** (mesh router) | ESP32 module, solar panel (5 W), 18650 battery, TP4056 charger, weatherproof enclosure, antenna module | $50 – $70 |

*Cost basis: a comparable ESP32-CAM wildlife monitoring node with solar power, battery, sensors and enclosure typically costs $60–80; adding the extended-range antenna module brings the total to the ranges shown.*

### Coverage range with antenna module

| Condition | Range with antenna module |
|---|---|
| Line-of-sight (LOS) | Up to 1.2 km |
| Non-line-of-sight (NLOS, e.g. through vegetation or obstacles) | Up to 400 m |

A single Edge Node with the antenna module can transmit approximately 1 km to a Backbone Node in open terrain, and maintain a reliable link at 400 m in forested or obstructed environments. With Backbone Nodes acting as repeaters, coverage extends further by chaining hops — suitable for large agricultural fields, forest boundaries or remote ranger stations.

### Summary specifications

| Specification | Value |
|---|---|
| Edge Node cost | $80 – $110 |
| Backbone Node cost | $50 – $70 |
| Range (LOS, with antenna) | ~1.2 km |
| Range (NLOS, with antenna) | ~400 m |
| Power source | Solar panel + 18650 battery (off-grid) |
| Sensors (Edge Node) | Camera, temperature, humidity, soil moisture, solar irradiance |
| Modularity | New sensors can be added without redesign |

### Key features and benefits

| Feature | Description | Benefit |
|---|---|---|
| Independent network | Operates without government infrastructure | Works in remote areas with no connectivity |
| Solar-powered | Off-grid operation with battery backup | Continuous operation during power outages |
| Edge AI | YOLO models run locally on nodes | Low latency, reduced bandwidth, privacy |
| Self-healing mesh | Data routes around failed nodes | High reliability and resilience |
| Multi-use case | Fire detection, wildlife tracking, herd counting, weather monitoring | Cost-effective for multiple stakeholders |
| Low cost | ESP32 is affordable (~$10 per node) | Scalable for large deployments |

---

## 5. What I Expect to End With

By the end of the programme (Wed 16 Dec 2026), I expect to have:

1. A **complete venture workbook** — one section per session, built on real customer evidence.
2. A **validated problem and customer segment** — a primary user (forest rangers / environmental agencies, or farmers) with an evidence log of interviews.
3. A **tested MVP hypothesis** — a one-page MVP test plan and, ideally, a working demonstration of two ESP32 nodes (1 Edge + 1 Backbone) with sensors and AI, relaying data over the mesh.
4. A **credible climate impact claim**, with a baseline, boundaries and at least two measurable indicators.
5. A **business model, pricing and 12-month cash plan**, plus a milestone-based funding strategy with two funding routes.
6. A **final pitch deck** (8–10 slides) covering problem, solution, impact, evidence, business model, competition, team, and next milestone/ask.
7. A **90-day action plan** for after Demo Day.
8. **Written jury feedback** from Demo Day and, potentially, a referral to incubation or acceleration programmes.
9. The **UNDP ICPSD digital certificate**, subject to meeting the three certificate conditions.

---

## 6. Expected Deliverables

| Deliverable | Description |
|---|---|
| Working prototype | 2 ESP32 nodes (1 Edge + 1 Backbone) with sensors and AI |
| Mesh network demo | Proof-of-concept showing data relay between nodes |
| Dashboard | Web interface for real-time monitoring and alerts |
| Documentation | Full technical documentation, setup guide and code repository |
| Final presentation | Slides and live demo for the capstone review |

---

## 7. My Personal Task List

### Before Friday 6 November

- [x] Read the Participant Guide
- [x] Choose one climate problem, one customer segment and one geography
- [x] Prepare a 60-second introduction (problem, solution, target customer)
- [x] Accept calendar invitations for all 12 sessions and Demo Day
- [x] Test session link, audio and camera
- [x] Join the cohort channel
- [x] Reply to confirmation email (deadline: COB Thu 5 Nov 2026)

### Weekly commitment

- [ ] Attend live sessions (Wed + Fri, 15:00–17:00 Damascus time)
- [ ] Produce and upload each weekly output by Friday
- [ ] Block ~6–8 hours per week (4h live + output + mentoring)
- [ ] Inform programme team in advance of any absence

### Mentoring

- [ ] Book Round 1 session (9–13 Nov)
- [ ] Book Round 2 session (23–27 Nov)
- [ ] Book Round 3 session (7–11 Dec)
- [ ] Prepare materials + 2 concrete questions before each session

### Masterclasses & optional learning

- [ ] Attend masterclasses from Week 2 (dates in cohort channel)
- [ ] (Optional) Complete relevant HP LIFE courses

### Final submission & Demo Day

- [ ] Upload first complete pitch draft before Session 12 (Mon 14 Dec)
- [ ] Submit final workbook, pitch deck and 90-day action plan by **Tue 15 Dec**
- [ ] Pitch at Demo Day — **Wed 16 Dec**

---

## 8. Session Tracker

Legend: ⬜ Not started · 🔄 In progress · ✅ Done

| # | Date | Session | Output | Status | Output file |
|---|---|---|---|---|---|
| 1 | Fri 6 Nov | Climate problem and first customer | Problem-and-customer page with market range; pitch outline | ✅ Done | `sessions/01-problem-and-customer/` |
| 2 | Wed 11 Nov | Customer discovery and value proposition | Value proposition, interview guide and evidence log | 🔄 In progress | `sessions/02-customer-discovery/` |
| 3 | Fri 13 Nov | Riskiest assumption and MVP test design | One-page MVP test plan | ⬜ Not started | — |
| 4 | Wed 18 Nov | Climate impact baseline and boundaries | Preliminary impact worksheet | ⬜ Not started | — |
| 5 | Fri 20 Nov | Competition and the route to adoption | Competition-and-adoption page | ⬜ Not started | — |
| 6 | Wed 25 Nov | Credible impact claims and measurement | Impact section with two indicators | ⬜ Not started | — |
| 7 | Fri 27 Nov | Business model and customer value | Business model page and positioning sentence | ⬜ Not started | — |
| 8 | Wed 2 Dec | Pricing and minimum viable cash plan | Provisional price, unit economics and 12-month cash plan | ⬜ Not started | — |
| 9 | Fri 4 Dec | Milestone-based funding strategy | Milestone-and-funding page with two funding routes | ⬜ Not started | — |
| 10 | Wed 9 Dec | Regulatory and market entry screening | Market-entry screening page | ⬜ Not started | — |
| 11 | Fri 11 Dec | IP decisions and priority risks | IP-and-risk page; first complete pitch draft | ⬜ Not started | — |
| 12 | Mon 14 Dec | Pitch rehearsal and the next 90 days | Revision list and 90-day action plan | ⬜ Not started | — |
| — | Tue 15 Dec | Final submission (no live session) | Workbook, pitch deck and 90-day action plan | ⬜ Not started | — |
| — | Wed 16 Dec | **Demo Day** | Live pitch | ⬜ Not started | — |

---

## 9. Key Dates

| Item | Date |
|---|---|
| Confirmation deadline | Thu 5 Nov 2026 |
| Programme start | Fri 6 Nov 2026 |
| Mentoring Round 1 | 9–13 Nov 2026 |
| Mentoring Round 2 | 23–27 Nov 2026 |
| Mentoring Round 3 | 7–11 Dec 2026 |
| Final submission | Tue 15 Dec 2026 |
| Demo Day | Wed 16 Dec 2026 |

---

## 10. Contacts

### Programme

| Role | Contact |
|---|---|
| Programme coordination | Halit Duran, PhD — halit.duran@undp.org |
| Lead Trainer | Mohammed Abdelaziz — mfathy@gmail.com |
| Trainer | Afonso Zinga — afonso1zinga@yahoo.co.uk |
| Cohort channel | [link to be shared] |

### Venture team

| Name | Email |
|---|---|
| Ahmad Deeb | ahmaddeebdev@gmail.com |
| Nimra Afzaal | nimraafzaal1998@gmail.com |
| Sular Albalkhi | sularalbalkhi@gmail.com |
| Zaid Aldeen Mohammad Kiki | kikizaid2@gmail.com |

---

## 11. Repository Structure

```
.
├── README.md
├── CONTEXT.md
├── .gitignore
├── assets/
│   └── logo/
│       └── sentinelmesh-logo.svg
├── sessions/
│   ├── 01-problem-and-customer/
│   ├── 02-customer-discovery/
│   ├── 03-mvp-test-plan/
│   ├── 04-impact-baseline/
│   ├── 05-competition-and-adoption/
│   ├── 06-impact-claims-and-measurement/
│   ├── 07-business-model/
│   ├── 08-pricing-and-cash-plan/
│   ├── 09-milestone-and-funding/
│   ├── 10-market-entry-screening/
│   ├── 11-ip-and-risk/
│   └── 12-pitch-rehearsal/
├── mentoring/
│   ├── round-1/
│   ├── round-2/
│   └── round-3/
├── customer-evidence/
│   └── evidence-log.md
├── workbook/
│   └── climate-founders-workbook.pdf
├── pitch/
│   ├── draft-v1.pptx
│   └── final-deck.pdf
├── action-plan/
│   └── 90-day-action-plan.md
├── firmware/
│   └── esp32-node/
│       ├── src/
│       ├── include/
│       ├── lib/
│       ├── platformio.ini
│       └── README.md
├── server/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── routes.py
│   │   └── services/
│   ├── migrations/
│   ├── tests/
│   ├── requirements.txt
│   ├── .env.example
│   └── README.md
└── mobile/
    ├── lib/
    ├── assets/
    ├── test/
    ├── pubspec.yaml
    └── README.md
```

### Code folders

| Folder | Purpose |
|---|---|
| `firmware/` | ESP32 node firmware — sensor reading, on-device YOLO inference, ESP-MESH networking, power management |
| `server/` | Backend API — ingests node data via gateway, stores readings and detections, serves the dashboard and mobile app |
| `mobile/` | Field-facing app — real-time alerts, sensor readings, detection logs |

---

## 12. Progress Log

| Date | Update |
|---|---|
| 04-Nov-2026 | Selected for the programme; received Participant Guide |
| 04-Nov-2026 | Chose climate problem, customer segment and geography |
| 04-Nov-2026 | Prepared 60-second introduction (Qatra — irrigation focus) |
| [date] | **Pivot:** venture reframed as SentinelMesh — decentralised solar-powered IoT mesh for environmental monitoring (fire, wildlife, herd, weather) |
| [date] | Defined two-tier node architecture, cost and coverage figures |
| [date] | Rewrote README for SentinelMesh |

---