# Session 4 — Riskiest Assumption and MVP Test Design: Follow-up

**Venture:** SentinelMesh — Monitoring without infrastructure.

**Session date:** Wed 18 Nov 2026

**Trainer:** Prof. Afonso Zinga

**Author:** Ahmad Deeb, Nimra Afzaal, Sular Albalkhi, Zaid Aldeen Mohammad Kiki

**Status:** ✅ Submitted

---

## Homework Task

> Use the session materials to rank three assumptions and draft the smallest useful test. State what you will measure, your success threshold and how the result will guide your next step.

---

## 1. Climate Problem & First Customer

- **Climate Problem:** Wildfires in Syria's remote forest areas are detected too late to contain because cellular coverage and grid power are absent where fires start (12,000 ha of natural forest lost in 2025, ≈2.0 Mt CO₂; 2,367 fire incidents in Q1 2026).
- **First Customer:** Syrian forest protection agencies — Ministry of Emergency and Disaster Management, General Organization for Remote Sensing (GORS / FIRMO platform), and civil defence units responsible for forest fire response.

---

## 2. Assumption Ranking

Formula: **Score = Impact × (6 – Evidence)** (Impact 1–5; Evidence 1–5 based on discovery to date).

| Rank | Assumption | Type | Impact | Evidence | Score | Smallest Useful Test |
|---|---|---|---|---|---|---|
| **A1** | An ESP32-CAM running a YOLOv8n model detects controlled smoke at 50–100 m in daylight with **≥ 80% recall** and **≤ 20% false positives**. | Technical | 5 | 1 | **25** | Controlled smoke bench/field test (30 trials) |
| **A2** | A forest ranger or agency dispatcher will act on an automated SentinelMesh alert without independent verification. | Demand | 5 | 2 | **20** | Structured interview + alert workflow simulation |
| **A3** | Hardware cost ($80–$110 per Edge Node) fits within the target agency's procurement budget for remote deployment. | Viability | 4 | 2 | **16** | Procurement review & desk research (including UNDP tender context) |

### Ranking Rationale

- **A1 (Score 25 — Technical):** Top risk. If the edge camera cannot reliably spot smoke at a practical distance, the core product value fails regardless of mesh range or budget fit.
- **A2 (Score 20 — Demand):** Second risk. Even if detection works technically, a slow or untrusted alert that requires manual verification defeats early containment.
- **A3 (Score 16 — Viability):** Third risk. Unit economics ($80–$110 per Edge Node) must align with institutional/donor procurement budgets, though early tender context (UNDP Syria early-detection tender, Nov 2025) provides slightly more initial signal than A1.

---

## 3. Smallest Useful Test (Testing Top Assumption: A1)

- **Hypothesis:** An ESP32-CAM running a YOLOv8n model, mounted at **2 m height**, detects controlled smoke at **50–100 m** in daylight with **≥ 80% recall** and **≤ 20% false positives** across **30 trials**.
- **What We Will Measure:**
  1. **Recall rate:** Share of smoke trials correctly flagged as smoke alerts.
  2. **False-positive rate:** Share of non-smoke frames/intervals falsely flagged as smoke alerts.
  3. **Alert latency:** Time elapsed from smoke introduction to alert generation.

### Pre-Set Success Thresholds

| Outcome | Condition | Action Rule |
|---|---|---|
| ✅ **Proceed** | Recall **≥ 80%** AND False positives **≤ 20%** | Advance to test A2 (Demand) and order long-range antenna modules to test mesh relay |
| 🔄 **Revise** | Recall **60–79%** OR False positives **20–35%** | Adjust camera mount height, test distance (e.g., 30 m), or lightweight model (e.g., TinyYOLO); re-run **once** |
| 🛑 **Stop** | Recall **< 60%** OR False positives **> 35%** | Halt camera-based edge AI approach at this price point and pivot to thermal / smoke-gas sensors (e.g., MQ-2) |

### Test Caps, Ownership & Permissions

- **Caps:** Maximum **3 weeks**, **≤ $250** budget, and **≤ 30 test runs**.
- **Owner & Observer:** **Ahmad Deeb** (build, execute, log); independent team observer (**Nimra Afzaal**, **Sular Albalkhi**, or **Zaid Aldeen Mohammad Kiki**) for scoring.
- **Dependencies & Permissions:** Safe outdoor daylight site with owner permission; controlled smoke source only (**no open flame / no live fire**); working ESP32-CAM node and fine-tuned YOLOv8n test setup. Results logged in `customer-evidence/evidence-log.md`.

---

## 4. How Results Guide the Next Step

- **If Proceed:** Run an alert workflow simulation and structured interview with a forest ranger/dispatcher to test **A2 (Demand)** using the prototype dashboard, while ordering long-range antenna modules to test mesh relay.
- **If Revise:** Tune mounting height, shorten distance (e.g., 30 m), or test an alternative lightweight model (e.g., TinyYOLO) and execute a single follow-up round of trials before deciding whether to proceed or stop.
- **If Stop:** Pivot away from camera-based edge AI on ESP32-CAM toward a thermal or smoke-gas sensor array (such as MQ-2) as the primary detection mechanism.