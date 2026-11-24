# Session 2 — Climate Action Categories & Project Examples

**Venture:** SentinelMesh — Monitoring without infrastructure.

**Session date:** Wed 11 Nov 2026

**Trainer:** Mohammed Abdelaziz (Lead Trainer)

**Author:** Ahmad Deeb, Nimra Afzaal, Sular Albalkhi, Zaid Aldeen Mohammad Kiki

**Status:** ✅ Submitted

---

## Homework Task

> Describe one climate problem, who experiences it and where. Choose the closest climate action category and suggest a first test.

This README is the submitted answer. Supporting files in this folder provide the full evidence and reasoning.

---

### 1. The Climate Problem

Wildfires in Syria's remaining forest areas are being detected too late to contain — and the same monitoring gap that causes this also blinds farmers and researchers to herd losses, wildlife decline, and soil and weather conditions in the same remote areas.

Syria lost **12,000 hectares** of natural forest in 2025 (≈**2.0 Mt CO₂**), recorded **2,367 fire incidents in Q1 2026** (up from 2,261 in Q1 2025), and has lost **40% of its 2000 tree cover** between 2001 and 2025 — with wildfire the single largest driver.

The root cause is the same for every use case: **the areas that most need monitoring are the areas with no infrastructure to monitor them.** Cellular coverage and grid power cannot be assumed after fourteen years of conflict, so forest rangers cannot detect fires early, farmers cannot track herds across remote pasture, and researchers cannot collect field data on wildlife or soil.

**One platform, multiple monitoring needs:**

| Need | Who is harmed when it goes unmet |
|---|---|
| Late wildfire detection | Forest agencies, civil defence, adjacent communities |
| Untracked herd losses | Farmers and pastoralists in remote grazing areas |
| No wildlife field data | Ecological researchers, conservation bodies, universities |
| No local soil/weather data | Farmers making irrigation and planting decisions |

---

### 2. Who Experiences It

**Primary customer (lead problem — wildfire):**
- Ministry of Emergency and Disaster Management
- General Organization for Remote Sensing (GORS) — Forest and Fire Monitoring Platform (FIRMO)
- Civil defence units responsible for forest fire response

**Secondary customers (same platform, different use case):**
- **Farmers and agricultural cooperatives** — herd counting, soil moisture and local weather data for irrigation and grazing decisions
- **Ecological researchers and universities** — automated wildlife detection and logging for species monitoring and field research

**Why they cannot solve it today:** every existing alternative depends on the infrastructure that is missing —

| Alternative | Limitation |
|---|---|
| Satellite alerts (VIIRS, MODIS) | Detection latency; coarse resolution; misses small ground fires and individual animals |
| Citizen reporting (phone calls) | Requires someone present with coverage; slow and unreliable |
| Government monitoring platform | Centralised; depends on remote sensing and weather data, not field-level |
| Commercial IoT sensor networks | Require connectivity and grid power; not designed for war-damaged infrastructure |
| Manual patrols and field surveys | Limited coverage; dangerous terrain; unexploded ordnance risk |

---

### 3. Where

Remote areas of Syria — forest boundaries, mountain remnants, agricultural fields and grazing land — particularly where:
- terrain is difficult and patrols are unsafe,
- cellular coverage is absent or unreliable,
- grid electricity is unavailable,
- and fires, herd losses, or wildlife activity therefore go unmonitored until damage is done.

Coastal and mountain forest remnants (including Cilician fir, *Abies cilicica*) are a priority for fire detection; adjacent agricultural and grazing land is a priority for herd counting and soil/weather monitoring.

---

### 4. Closest Climate Action Category

**Main topic: Climate data and early warning**

**Related topic: Climate adaptation and resilience** — reducing harm from climate-driven hazards (wildfire, drought) to people, livelihoods and ecosystems.

**Why this category:** SentinelMesh's value is the **time between an event and the alert that triggers a response** — whether that event is a fire ignition, a herd straying, or a wildlife sighting. That is the definition of early warning: field data collected, processed at the edge, and delivered to the person who acts on it.

The Session 2 slide's own subcategory examples for this topic — *Early warning* (Brazil's Cemaden) and *Local monitoring* (rain gauges changing irrigation decisions) — describe exactly this pattern. The multi-use capability (fire, herd, wildlife, soil) is a **feature of the same node architecture**, not a separate product.

**Who acts on the data:**
- **Fire alert** → forest ranger or civil defence dispatcher decides where to send a response team
- **Herd count / location** → farmer decides where to move livestock or when to search
- **Wildlife detection** → researcher logs species presence and population trends
- **Soil/weather reading** → farmer decides when to irrigate or plant

---

### 5. First Test

**Controlled smoke test with a two-node mesh** — testing the lead problem first, with secondary use cases validated afterward on the same hardware.

Deploy one ESP32-CAM Edge Node and one Backbone Node approximately **400 m apart in obstructed (non-line-of-sight) terrain**. Introduce controlled smoke at the Edge Node and measure:

1. **Detection** — does the on-device YOLO model raise a smoke alert?
2. **Latency** — what is the time from smoke introduction to alert?
3. **Relay** — does the alert reach the Backbone Node over the mesh?

**Why fire first:** it is the highest-urgency, institutionally-funded problem (UNDP Syria issued an early-detection tender in Nov 2025), and it exercises the full stack — camera capture, edge AI inference, mesh relay, and alert delivery — that the secondary use cases also depend on.

**Secondary tests (same hardware, after the fire test):**

| Use case | Test | What it measures |
|---|---|---|
| Herd counting | Point the Edge Node at a controlled group of animals (or a labelled image set) | Count accuracy and inference time |
| Wildlife detection | Run the model against a labelled set of local species images | Detection and classification accuracy |
| Soil/weather monitoring | Compare sensor readings against a calibrated reference over 24 hours | Sensor accuracy and data relay reliability |

**What the first test proves:** assumptions **A5** (smoke/fire detection via ESP32-CAM + YOLO is credible) and **A7** (mesh range is sufficient for target terrain) from the value proposition — the two assumptions that, if false, invalidate the entire platform, not just the fire use case.

**What success looks like:** a smoke alert raised within a defined window (target: < 2 minutes), received at the Backbone Node, with a false-positive rate low enough that a ranger would act on it — and the same node then successfully counting a herd and logging a wildlife detection.

**What failure tells us:** if detection fails at 400 m NLOS, the mesh range assumption needs revision (more backbone nodes or LoRa); if detection is unreliable, the edge-AI approach needs a different model or a companion edge device — and that finding applies to every use case on the platform.

---

### 6. One-Sentence Version

> SentinelMesh gives Syrian forest agencies, farmers and researchers a solar-powered, self-healing mesh network that detects fires, counts herds, logs wildlife and reports soil and weather conditions at field level — relaying alerts and data without connectivity or grid power, so problems are caught while they can still be acted on.