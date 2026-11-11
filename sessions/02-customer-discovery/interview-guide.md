# Interview Guide

**Venture:** SentinelMesh — Monitoring without infrastructure.

**Session:** 2 — Customer discovery and value proposition

**Date:** 11 November 2026

**Author:** Ahmad Deeb

**Purpose:** Structured guide for customer discovery conversations with Syrian forest protection and environmental monitoring stakeholders.

---

## 1. How to use this guide

This is a **discovery interview**, not a sales pitch. The goal is to learn how forest fire detection and response actually works today, where it fails, and what would need to be true for an automated field-level detection system to be adopted.

**Core rules (The Mom Test):**
- Talk about **their life and past behaviour**, not your idea .
- Ask about **specific past events**, not hypothetical futures .
- **Listen more than you talk** — aim for the interviewee speaking 70–80% of the time .
- **Never ask** "Would you use this?", "Do you think this is a good idea?", or "How much would you pay?" .
- Compliments are not data. Steer back to what they actually did .

**Target interviewees:**
- Forest rangers and field patrol staff
- Ministry of Emergency and Disaster Management officials
- General Organization for Remote Sensing (GORS) staff working on the FIRMO forest monitoring platform
- Civil defence responders with forest fire experience
- NGO/donor project staff working on wildfire or early warning programmes (e.g., FAO/ECHO projects) 

**Target: 3–5 interviews this week.** Even 2 completed interviews is meaningful evidence for Session 2.

---

## 2. Interview structure (30–40 minutes)

### Part A: Welcome and context (3–5 min)

**Purpose:** Establish rapport, confirm they fit the customer profile, and make clear this is research not sales.

**Opening script:**
> "Thank you for taking the time. I'm Ahmad, working on a project through a UNDP pre-incubation programme. I'm trying to understand how forest fire detection and response actually works in Syria today — what happens on the ground, what's difficult, what works. This is not a sales conversation. There are no right or wrong answers. I'm just trying to learn from your experience. Is it okay if I take notes?"

**Customer characteristics questions:**
1. What is your role, and what area do you cover?
2. How long have you been doing this work?
3. Walk me through a typical week — what does your monitoring and patrol work look like?

### Part B: Exploration of past experiences — the core (15–20 min)

**Purpose:** Understand real fire events, detection methods, and pain points through specific past examples.

**Question 1 — The last fire:**
> "Walk me through the last forest fire you were involved with. How was it first detected? What happened from that moment?"

*Follow-up probes:*
- How long between ignition and the first alert reaching responders?
- Who reported it? How did they report it?
- What was the outcome — how many hectares burned?
- What would have changed if you had known 30 minutes earlier? An hour earlier?

**Question 2 — Detection methods today:**
> "How do you currently find out about fires in your area? What are all the ways — formal and informal?"

*Probes:*
- Do you use satellite alerts? How quickly do they arrive? Are they useful?
- Do citizens call in reports? How often?
- Do you have any automated sensors or cameras now?
- What percentage of your area has reliable mobile phone coverage?

**Question 3 — The hardest part:**
> "What's the hardest part about detecting fires early in your area?"

*Probes:*
- Is it terrain? Distance? Lack of people? Lack of equipment?
- Are there areas you simply cannot monitor?
- What happens in those areas?

**Question 4 — Current tools and costs:**
> "What monitoring equipment or systems do you currently have? What does it cost to operate and maintain?"

*Probes:*
- Do you have any sensor networks, cameras, or weather stations?
- Who maintains them? What breaks?
- What's the budget for monitoring, if any?

### Part C: Problem impact and organisational context (5–10 min)

**Purpose:** Understand the scale of the problem and how adoption decisions would be made.

**Question 5 — Cost of late detection:**
> "When a fire is detected late, what does that cost — in hectares, in response effort, in budget?"

**Question 6 — Decision-making:**
> "If a new monitoring system were to be considered, who would need to approve it? What would that process look like?"

*Probes:*
- Is there budget for this, or would it need donor funding?
- Has anything like this been tried before? What happened?

**Question 7 — Trust and adoption:**
> "What would you need to see to trust an automated alert from a sensor system?"

*Probes:*
- Would a camera-based smoke detection alert be credible?
- Who would need to validate it before responders acted on it?

### Part D: Wrap-up and ask (3–5 min)

**Purpose:** Capture referrals and next steps.

**Closing questions:**
1. "Is there anything I should have asked but didn't?"
2. "Who else should I speak to — someone who knows the detection problem well?"
3. "Would you be willing to stay in touch as I develop this?"

**Commitment ask (optional but valuable):**
> "Would you be open to a short follow-up conversation in a few weeks, once I have a prototype concept to show?"

*The answer tells you whether they actually care* .

---

## 3. Dangerous questions to avoid

| Don't ask | Why it's bad | Ask instead |
|---|---|---|
| "Would you use a system like this?" | Hypothetical future; produces false positives  | "Walk me through the last time you had a fire. How did you find out?" |
| "Do you think this is a good idea?" | Opinion about your idea, not their life  | "What's the hardest part about detection today?" |
| "How much would you pay for this?" | Imaginary budget  | "What are you currently spending on monitoring?" |
| "What features would you want?" | Wish list disconnected from workflow  | "What have you tried that didn't work? Why?" |
| "Is there a need for this?" | Everyone says yes politely | "What happens in the areas you can't monitor?" |

---

## 4. What to listen for (signals that matter)

**Strong signals:**
- Specific fire events with details (dates, locations, response times) — these are your evidence.
- Expressions of frustration with current detection ("by the time we know, it's too late").
- Mention of areas with no coverage or no patrols.
- Existing workarounds (citizen networks, informal phone trees).
- Named budget holders or procurement processes.
- Referrals to other people to speak with.

**Weak signals (do not count as evidence):**
- "This sounds interesting" / "Good idea" — compliments, not data .
- "I'm sure farmers would love this" — speculation about others.
- "We need everything" — generic wish lists.

**Red flags to record honestly:**
- "We already have satellite alerts that work fine" — challenges your value proposition.
- "There's no budget for anything new" — challenges feasibility.
- "The Ministry would never approve a foreign system" — challenges adoption.

---

## 5. After the interview

Within 2 hours, add a row to `customer-evidence/evidence-log.md` with:
- Interviewee code, role, date, duration
- Key insights (verbatim quotes where possible)
- Which assumption (A1–A7 from the value proposition) was confirmed, challenged, or left open
- Follow-up actions

---

## 6. Assumptions this guide tests

| # | Assumption | Primary questions |
|---|---|---|
| A1 | Fires are detected too late for effective containment | Q1, Q2, Q5 |
| A2 | Target areas lack reliable coverage and power | Q2 (coverage), Q4 (equipment) |
| A3 | Agencies have budget or donor funding | Q4, Q6 |
| A5 | Smoke/fire detection via ESP32-CAM + YOLO is credible | Q7 (trust) |
| A6 | Agencies will act on automated alerts | Q7 |

*Note: A4 (cost affordability) and A7 (mesh range sufficiency) are better tested through MVP and cost modelling than interviews.*

---
