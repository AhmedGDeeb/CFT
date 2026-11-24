# SentinelMesh — Assumption Map (Session 4)

**Venture:** SentinelMesh — Monitoring without infrastructure[cite: 1, 2].

**Session date:** Wed 18 Nov 2026

**Trainer:** Prof. Afonso Zinga[cite: 3]

**Authors:** Ahmad Deeb, Nimra Afzaal, Sular Albalkhi, Zaid Aldeen Mohammad Kiki[cite: 2, 3]

---

## 1. Scoring Method & Scale

$$\text{Risk Score} = \text{Impact} \times (6 - \text{Evidence})$$

- **Impact (1–5):** How severely the venture or lead wildfire early-warning use case is harmed if the assumption is false (1 = minor inconvenience, 5 = existential/product-breaking).
- **Evidence (1–5):** Strength of validated evidence gathered so far (1 = pure guess/untested, 5 = strong empirical/contractual proof).
- **Score Range:** `5` (lowest risk: $1 \times (6 - 1)$ or $5 \times (6 - 5)$) to `25` (highest risk: $5 \times (6 - 1)$).

---

## 2. Full Assumption Map by Category

### A. Demand (Desirability)

| ID | Assumption | Impact | Evidence | Score | Smallest Test / Validation Method |
|---|---|---|---|---|---|
| **D1** | Forest rangers or agency dispatchers will act on an automated SentinelMesh alert without independent verification. | 5 | 2 | **20** | Structured interview + alert workflow simulation with ranger/dispatcher[cite: 3] |
| **D2** | Agencies prefer real-time field alerts over existing alternatives (VIIRS/MODIS satellite alerts, phone reports, centralised platforms, manual patrols)[cite: 2]. | 4 | 2 | **16** | Comparative discovery interviews with agency/civil defence stakeholders |
| **D3** | Secondary users (farmers/cooperatives for herd/soil/weather; researchers/universities for wildlife/field data) value the same node architecture enough to support multi-use expansion[cite: 1, 2]. | 3 | 1 | **12** | 3–5 short discovery interviews with farmers and researchers |

### B. Technical (Feasibility)

| ID | Assumption | Impact | Evidence | Score | Smallest Test / Validation Method |
|---|---|---|---|---|---|
| **T1** | An ESP32-CAM running a YOLOv8n model detects controlled smoke at 50–100 m in daylight with **≥ 80% recall** and **≤ 20% false positives**[cite: 3]. | 5 | 1 | **25** | 30-trial controlled smoke bench/field test (2 m mount, no open flame)[cite: 3] |
| **T2** | A mesh link carries alerts reliably across target remote/obstructed terrain (e.g., ~400 m NLOS or multi-hop relay) with acceptable latency and packet loss[cite: 2, 3]. | 5 | 2 | **20** | Two-node field range & relay test with antenna modules |
| **T3** | Solar panel + battery + deep-sleep/edge-AI duty cycling sustains continuous off-grid operation without grid power or cellular coverage[cite: 1, 2]. | 4 | 2 | **16** | Off-grid power draw & duty-cycle bench test with solar/battery pack |
| **T4** | Secondary edge-AI/sensor tasks (herd counting, wildlife detection, DHT22/soil/MQ-2 readings) run reliably on the node stack[cite: 1, 2, 3]. | 3 | 2 | **12** | Controlled image-set & 24-hour sensor reference comparison[cite: 2] |

### C. Viability (Business & Cost)

| ID | Assumption | Impact | Evidence | Score | Smallest Test / Validation Method |
|---|---|---|---|---|---|
| **V1** | Hardware cost ($80–$110 per Edge Node; $50–$70 per Backbone Node) fits within agency/donor procurement budgets for remote deployment[cite: 1]. | 4 | 2 | **16** | Procurement desk review & tender/budget comparison (e.g., UNDP early-detection context)[cite: 2] |
| **V2** | Institutional or donor/grant funding channels (such as UNDP/climate/disaster resilience programmes) can fund initial pilots and hardware rollouts[cite: 1, 2]. | 4 | 2 | **16** | Funding route mapping & stakeholder/programme feedback |
| **V3** | Maintenance, replacement, and field servicing costs remain sustainable across remote deployments without creating ongoing agency burden. | 3 | 1 | **12** | Unit maintenance & replacement cost model in cash/unit plan |

### D. Permission (Access, Safety & Governance)

| ID | Assumption | Impact | Evidence | Score | Smallest Test / Validation Method |
|---|---|---|---|---|---|
| **P1** | Relevant authorities/site owners will grant permission to test and deploy monitoring nodes in target forest/remote areas[cite: 1, 2]. | 4 | 1 | **16** | Stakeholder inquiry on deployment permissions & site access rules |
| **P2** | Field testing and remote deployments can follow strict safety protocols (no live fire during smoke tests; safe routing around terrain/UXO hazards)[cite: 2, 3]. | 4 | 2 | **12** | Safety checklist & site-permission verification before any test run[cite: 3] |
| **P3** | Data handling and alert integration with agency workflows (e.g., Ministry of Emergency and Disaster Management, GORS/FIRMO, civil defence) meet operational expectations[cite: 1, 2, 3]. | 3 | 1 | **12** | Discovery question on alert format, channels, and reporting workflows |

---

## 3. Priority Order & Testing Sequence

1. **Immediate Priority — T1 (Score 25):** Run the 30-trial controlled smoke test on ESP32-CAM + YOLOv8n within the 3-week / ≤ $250 caps[cite: 3].
2. **Next Priority — D1 & T2 (Score 20 each):** Pair ranger/dispatcher workflow simulation (D1) with mesh range/relay testing (T2), while advancing procurement/permission checks (V1, P1 — Score 16) in parallel[cite: 1, 2, 3].
3. **Expansion / Secondary — D3 & T4 (Score 12 each):** Validate herd counting, wildlife logging, and soil/weather sensing only after the core wildfire detection and alert loop proves credible[cite: 1, 2].