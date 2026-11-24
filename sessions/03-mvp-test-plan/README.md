# One-Page RAT Plan — SentinelMesh

**Session 3 — Riskiest assumption and MVP test design**

**Date:** 13 November 2026

**Trainer:** Prof. Afonso Zinga (Riskiest assumption and MVP test design), Dr Amani Mohamed Ali (Climate problem and first customer), 

**Author:** Ahmad Deeb, Nimra Afzaal, Sular Albalkhi, Zaid Aldeen Mohammad Kiki

**Venture:** SentinelMesh — solar-powered, self-healing IoT mesh for wildfire early detection in remote Syria

**Status:** ✅ Submitted
---

## 1. Climate Problem

Wildfires in Syria's remote forest areas are detected too late to contain because cellular coverage and grid power are absent where fires start. Syria lost 12,000 ha of forest in 2025 (≈2.0 Mt CO₂) and recorded 2,367 fire incidents in Q1 2026.

**First customer:** Syrian forest protection agencies — Ministry of Emergency and Disaster Management, GORS/FIRMO platform, civil defence units.

---

## 2. Assumptions ranked (top three)

Score = Impact × (6 – Evidence), per the Session 3 method.

| Rank | Assumption | Type | Impact | Evidence | Score | Smallest test |
|---|---|---|---|---|---|---|
| **A1** | An ESP32-CAM running a YOLO model detects smoke at ≥ 80% recall with < 20% false positives, at a distance of 50–100 m in daylight | Technical | 5 | 1 | **25** | Bench test with controlled smoke |
| **A2** | A two-node mesh link carries the alert ≥ 400 m in obstructed (NLOS) terrain with < 5 s latency and < 5% packet loss | Technical | 5 | 2 | **20** | Field range test, two nodes |
| **A3** | A forest ranger or agency officer would act on an automated alert from this system without independent verification | Demand | 5 | 2 | **20** | Interview + letter of intent or workflow simulation |

**Why A1 is riskiest:** if the camera cannot see smoke reliably at useful range, the entire product concept fails — not just one feature. Evidence today is strong only on generic hardware (ESP32-CAM works, YOLO runs) but **not** on smoke detection performance at range.

---

## 3. The Test — A1 (Riskiest)

**Hypothesis:** An ESP32-CAM with a YOLOv8n model, mounted at 2 m height, detects controlled smoke at 50–100 m in daylight with ≥ 80% recall and ≤ 20% false positives across 30 trials.

**Metric:** (a) recall — smoke events correctly flagged; (b) false-positive rate — non-smoke frames flagged; (c) time from smoke introduction to alert.

**Threshold (set before the test):**
- ✅ **Proceed** if recall ≥ 80% AND false-positive ≤ 20% across 30 trials
- 🔄 **Revise** if recall 60–79% OR false-positive 20–35% — adjust model, distance or camera mount, re-test once
- 🛑 **Stop** if recall < 60% OR false-positive > 35% — the edge-AI approach at this price point is not viable

**Caps:** 3 weeks; ≤ $250 (one ESP32-CAM, one Backbone node, enclosure, battery, controlled smoke source); ≤ 30 test runs.

**Owner:** Ahmad Deeb (build, run, record). Independent observer for scoring: one team member (Nimra, Sular or Zaid).

**Dependencies:**
- One working ESP32-CAM + Backbone node pair (firmware from `firmware/esp32-node/`)
- A YOLOv8n model fine-tuned or validated on smoke imagery (public smoke datasets + local capture)
- A safe outdoor test site with permission (university yard, farm, or open land)
- No live fire — controlled smoke source only (smoke pellets or a contained cold-smoke generator)

**Conditions / permission:** outdoor daylight test only; no open flame; site owner permission; note that this is a bench/field test, not a certified fire test.

**Decision rule:** Proceed / revise / stop as above. Result recorded in `customer-evidence/evidence-log.md` and carried into the Session 4 follow-up.

---

## 4. What This Test Can and Cannot Establish

| Can establish | Cannot establish |
|---|---|
| Whether smoke detection works at 50–100 m in daylight | Whether it works at night or in rain/fog (later test) |
| Whether the model is accurate enough to generate a credible alert | Whether agencies trust or act on the alert (that is A3) |
| Whether latency is acceptable for early warning | Whether the full mesh relays reliably at 400 m (that is A2) |

**Next tests (queued, same hardware):**
- **A2** — two-node field range test at 400 m NLOS, measuring latency and packet loss
- **A3** — structured interview with a ranger/agency officer + one letter of intent or workflow simulation

---

## 5. One-Sentence Summary

> We will test whether an ESP32-CAM running YOLO can detect controlled smoke at 50–100 m with ≥ 80% recall and ≤ 20% false positives across 30 trials in 3 weeks under $250; if it cannot, the SentinelMesh concept as designed is not viable at this price point and we revise or stop before spending on a field pilot.

---

### Notes

- **Why this is a RAT, not an MVP:** the slides define a RAT as the smallest experiment that tests the one belief the venture cannot survive being wrong about. A1 is that belief. We are not building a working product or running a field pilot — we are running a bench/field test with one node and a smoke source.
- **Assumption types are mixed (Technical ×2, Demand ×1)** — per the slide, each needs a different kind of test, so A1 and A2 are performance tests and A3 is a demand/trust test.
- **The threshold is set before the test** so the result cannot be reinterpreted afterward (slide: "set stop rules before the test").

Do you want me to also produce the **A2 and A3 test cards** in the same format, so the full Session 3 package is ready to submit?