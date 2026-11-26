# Session 6 — Credible Impact Claims and Measurement

**Venture:** SentinelMesh — Monitoring without infrastructure.

**Session date:** Wed 25 Nov 2026

**Trainer:** Dr Amani Mohamed Ali

**Author:** Ahmad Deeb, Nimra Afzaal, Sular Albalkhi, Zaid Aldeen Mohammad Kiki

**Status:** ✅ Submitted

---

## 1. Two Indicators

### Indicator 1: Detection-to-Alert Time
- **Change to track:** Decrease in the time it takes for a wildfire to be detected and reported to responders.
- **Indicator & Unit:** Time from ignition/start of smoke to alert delivery (measured in **minutes**).
- **Data Source:** SentinelMesh gateway logs and dashboard timestamps (compared against historical Ministry/GORS or SANA logs).
- **Collection Frequency:** Continuous (automated logging); aggregated and reviewed monthly during the fire season.
- **Responsible:** Ahmad Deeb (Technical lead).

### Indicator 2: Hectares of Forest Burned per Event
- **Change to track:** Reduction in the physical damage caused by wildfires.
- **Indicator & Unit:** Hectares of forest burned per individual fire event (measured in **hectares/fire**).
- **Data Source:** Global Forest Watch (GFW) satellite data, cross-referenced with SANA/ministry incident reports.
- **Collection Frequency:** Annually at the end of the wildfire season (comparing 2026 baseline to 2027+ post-deployment data).
- **Responsible:** Nimra Afzaal or Sular Albalkhi (Research & Impact lead).

---

## 2. Baselines

### Baseline for Indicator 1 (Detection Time)
- **Starting value:** Currently being established via customer interviews. Anecdotal evidence suggests detection takes hours (or is too late) due to reliance on visual sighting.
- **Measurement period:** 2025/2026 fire season.
- **Location/Group:** Remote forest areas in Syria (coastal/mountain regions).
- **Source & Method:** Ministry/GORS incident logs. *If official precise logs are unavailable, we will record the current baseline via structured interviews with forest rangers, asking them to estimate the average time from ignition to dispatch.*
- **Future Comparison:** Will use the same interview method and dashboard logs to compare "before and after" using the exact same metric (minutes).

### Baseline for Indicator 2 (Hectares Burned)
- **Starting value:** 12,000 hectares lost across natural forest areas in 2025 (based on GFW data).
- **Measurement period:** Full 2025 calendar year.
- **Location/Group:** Syria national forest boundaries.
- **Source & Method:** Global Forest Watch (GFW) platform, accessed [Date: 25 Nov 2026]. Method is satellite tree-cover loss analysis.
- **Future Comparison:** We will measure the same geographical areas post-deployment. 

---

## 3. Climate Impact Claim

> **Claim Structure:** 
> **"Our** solar-powered IoT mesh network **is expected to** reduce the time from wildfire ignition to responder alert by up to 90% (from hours to under 2 minutes) **for** the Ministry of Emergency and Disaster Management and GORS/FIRMO **over** the pilot year, **based on** the technical latency thresholds established in our Session 3 MVP test plan and the operational assumption that automated alerts bypass the need for visual confirmation by a human bystander."

- **Claim Label:** **Expected** (This is a forecast based on our technical architecture, not yet a Measured result).
- **Evidence We Have:** 
  - Technical specs: Our mesh nodes relay alerts with < 5 s latency (target from our Session 3 test plan).
  - Problem scale: 12,000 ha lost in 2025 (GFW) indicating current detection is failing.
- **Gaps & Plan:** We do not have field data from a deployed mesh yet. *How we will fill it:* We will run a controlled test (A1/A2 from Session 3) to prove the technical latency, and deploy a pilot to measure real-world ignition-to-alert time, comparing it to the 2025 baseline.

---

## 4. Testing Assumptions

Here are the two riskiest assumptions in our Theory of Change:

### Assumption 1: Technical Reliability
- **Assumption:** An ESP32-CAM running YOLO can accurately detect smoke at 50–100m in daylight with ≥ 80% recall and ≤ 20% false positives.
- **Outcome at risk:** The *Immediate Results* (fast alerts). If the AI produces too many false positives (e.g., fog, dust), responders will ignore the alerts (alert fatigue). If it misses smoke, the system fails entirely.
- **Quick Test:** Controlled smoke test at 50–100m.
- **Check/When:** Ahmad Deeb, within 3 weeks (Session 3 RAT plan). 
- **Support Threshold:** Recall ≥ 80%, False Positives ≤ 20%.

### Assumption 2: Institutional Trust
- **Assumption:** A forest ranger or dispatcher will act on an automated SentinelMesh alert without needing to send a patrol to verify it first.
- **Outcome at risk:** The *Longer-term Impact* (fewer hectares burned). If they wait to verify, the fire grows, and we achieve zero reduction in response time despite the technology working.
- **Quick Test:** Workflow simulation and structured interviews with 2–3 rangers/Ministry officials.
- **Check/When:** Team via evidence log, by Dec 7 (Round 3 mentoring).
- **Support Threshold:** At least 2 out of 3 officials state they would dispatch a team based on the dashboard alert combined with a metadata snapshot (image).

---

## 5. Revisiting the 2030 Postcard

**The 2030 Postcard (Imagined):**
> *"Dear SentinelMesh team,*
> *Last week, a fire started in the Cilician fir forest at 2:00 PM. By 2:04 PM, our response team in the valley had the exact GPS coordinates and a photo of the smoke on our dashboard. We stopped it before it burned more than half a hectare. My team didn't have to hike for hours into the dark to find it. The forest is still standing."*
> — *Commander, Syrian Civil Defence*

**The Indicator:** 
The indicator that proves this postcard is real is **Indicator 1: Detection-to-Alert Time (minutes)** combined with **Indicator 2 (hectares burned per event)**. The postcard specifically describes the time gap shrinking (from hours of hiking to 4 minutes) and the physical outcome (fire stopped at half a hectare instead of thousands). 