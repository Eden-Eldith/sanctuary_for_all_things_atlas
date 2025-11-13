---
{"dg-publish":true,"permalink":"/finalized-work/kirk-protocol-v4/","created":"2025-09-19T10:03:17.275+01:00","updated":"2025-09-21T18:53:08.994+01:00"}
---

# The Kirk Protocol v4.0
## Security Framework for Open-Air Political/Public Speaking Events

---

## Foreword

As a British 25-year-old man, I have watched Charlie Kirk for many years on YouTube. I respected his right to freedom of speech whilst also learning a great deal from him about how the mainstream media operates, and where hidden data and statistics could be found to form an informed opinion.

Whilst I may not have agreed with some of his points, I looked up to him as a strong, intelligent man who was also a good father and a loving husband – everything a man strives to be.

His assassination in September 2025 was not simply the silencing of a commentator; it was the removal of a teacher, a father, and a builder of community. The failure to protect him highlights a gap in how society safeguards those who speak in public spaces.

This framework is not just a technical recommendation. It is a call to ensure that future speakers – whatever their political stance – are protected from targeted violence when exercising their right to speak freely in front of others.

I have also come to realize something else: the consequences of propaganda are not abstract. When intolerance of opinions is normalized, when one side demonizes voices it cannot defeat in debate, the end result is violence. Charlie Kirk's death is proof of this. I do not agree with political violence, and I do not agree with intolerance of speech. Free societies cannot survive when ideas are met with bullets instead of arguments.

---

## 1. Threat Model

### Primary Threat Assessment
- **Primary Risk:** Precision rifle fire from elevated vantage points overlooking stage/crowd.  
- **Context:** Charlie Kirk assassination (09/10/2025, Utah Valley University) demonstrated vulnerability – 200-yard line-of-sight shot from Losee Center into exposed courtyard stage.  
- **Assumption:** Speaker is a high-profile political figure (not necessarily state-protected).

### Dynamic Threat Assessment (NEW)
Each event must include comprehensive threat analysis beyond the primary sniper threat:

- **Counter-Surveillance Detection:** Conduct sweeps for reconnaissance activity 72 hours before event
- **Alternative Threat Analysis:** "If not a sniper, then what?" planning matrix:
  - IED/VBIED threats (vehicle approach routes)
  - CBRN considerations (air circulation systems)
  - Drone-borne threats (aerial denial zones)
  - Coordinated perimeter attacks (multiple actors)
- **Armor-Piercing Defense:** All ballistic barriers must be rated to stop at least one round of .30-06 M2 AP ammunition
- **Insider Risk Assessment:** Background checks for all staff with venue access 48 hours prior

---

## 2. Core Measures

### A. Ballistic Barriers

#### Stage Shielding
- Install **NIJ Level III+ or Level IV ballistic glass panels** in front of podium/speaker area
- Panels must meet calculated height requirements (see Section 2.E)
- Transparent to allow visibility without exposure
- Must withstand armor-piercing rounds (minimum .30-06 M2 AP rated)

#### Side Panels
- Deploy modular barriers at **45° angles** to block oblique lines of fire
- Minimum NIJ Level III+ rating

#### Barrier Effectiveness Table

> **Illustrative survivability modeling (non‑normative):**  
> The percentages below are modeled estimates for planning, not certifications. They combine: (1) baseline torso GSW fatality rates from trauma literature; and (2) whether a barrier **rated for the stated threat** cleanly stops the round. Actual outcomes vary with shot placement, distance, hit count/spacing, angle, spall, and time to medical care. This section expresses **opinionated modeling**, not NIJ/UL/EN guarantees.

| Caliber    | Weapon Type    | No Barrier Survival Rate | With NIJ III+ Barrier | With NIJ IV Barrier |
| ---------- | -------------- | ------------------------ | --------------------- | ------------------- |
| .22 LR     | Handgun/Rifle  | 65%                      | 100%                  | 100%                |
| 9mm        | Handgun        | 55%                      | 100%                  | 100%                |
| .223/5.56  | AR-15 type     | 25%                      | 90%                   | 100%                |
| .308/7.62  | Hunting/Sniper | 15%                      | 80%                   | 99%                 |
| .30-06     | Hunting/Sniper | 10%                      | 65%                   | 95%                 |
| .338 Lapua | Long-range     | 5%                       | 40%                   | 90%                 |
| .50 BMG    | Anti-materiel  | <1%                      | 10%                   | 60%                 |

*Survival rates based on center-mass hits without immediate medical intervention

![Barrier_vs_Non-barrier chart 2.png](/img/user/Finalized%20work/Barrier_vs_Non-barrier%20chart%202.png)

### B. Vantage Point Hardening

#### Permanent Solutions
- Retrofit high-risk buildings with **ballistic glass or laminated ballistic film**
- Install **angled architectural louvres** to break line-of-sight
- Establish permanent counter-sniper positions on key buildings

#### Event-Specific Solutions
- Secure all buildings within calculated threat radius (see formula below)
- Post **armed overwatch units** with overlapping fields of fire
- Deploy portable screening systems for temporary events

### C. Access Control

#### Venue Perimeter
- Establish secure perimeter at **minimum 100 yards** from stage
- Implement layered security zones:
  - Outer perimeter: Vehicle screening
  - Middle perimeter: Magnetometers and bag checks
  - Inner perimeter: Credential verification

#### Building Control
- Lock and monitor all windows/doors with line-of-sight
- Station security at all roof access points
- Install temporary CCTV on all approach routes

### D. Counter-Sniper Readiness

#### Surveillance Assets
- Thermal/optical scopes covering all vantage zones
- Drone surveillance for real-time overwatch
- Acoustic shot detection systems

#### Deployment Protocol
- Minimum 2 counter-sniper teams per event
- Overlapping fields of view mandatory
- Direct encrypted comms to ground units
- 30-second response time requirement

### E. Barrier Height Calculation Formula (NEW)

To determine minimum barrier height based on surrounding buildings:

```
H_barrier = H_speaker + [(D_threat × tan(θ)) - H_stage]

Where:
- H_barrier = Required barrier height (meters)
- H_speaker = Speaker's height when standing (typically 1.8m)
- D_threat = Distance to tallest building within 500 yards
- θ = Angle of depression from highest vantage point
- H_stage = Stage elevation above ground level

Safety Factor: Add 0.5m to calculated height
```

**Quick Reference Table:**

| Building Height | Distance | Minimum Barrier Height |
|----------------|----------|----------------------|
| 3 floors (10m) | 100m | 2.8m |
| 5 floors (17m) | 200m | 3.2m |
| 8 floors (27m) | 300m | 3.6m |
| 10+ floors (33m+) | 400m | 4.0m |

---

## 3. Policy Recommendations

### 3.1 Speaker Classification System (ENHANCED)

**Objective Metrics for Tier Classification:**

#### Tier 1: State-Protected Figures
- Current/former heads of state
- Cabinet-level officials
- Supreme Court justices

#### Tier 2: High-Profile Public Figures
Requires meeting **TWO** of the following criteria:
- National name recognition >40% (verified polling data)
- Verified social media following >1 million
- Regular appearances on national media (>12 annually)
- Credible threat assessment from law enforcement
- Speaking fees exceeding $50,000 per event

#### Tier 3: Regional/Local Figures
- State/local politicians
- Regional media personalities
- Academic speakers without national profile

### 3.2 Mandated Security Standards

1. **Ballistic Barriers Required** for all Tier 1 and Tier 2 speakers
2. **Venue Risk Assessment** mandatory 30 days before event
3. **Threat Radius Mapping** of all vantage points within:
   - 1,000 yards for Tier 1
   - 500 yards for Tier 2
   - 200 yards for Tier 3
4. **Liability Framework:** Venues accepting responsibility for security failures

### 3.3 Non-Cooperation Protocol 

When venues refuse to implement required security measures:

#### Pre-Event Requirements
- Written security agreements required **before** event announcement
- Specific access authorizations documented
- Alternative venue identified and pre-cleared

#### Response to Non-Compliance
1. **Immediate Cancellation** if security requirements not met
2. **Public Statement Template:**
   > "In the interest of attendee and speaker safety, we cannot proceed with the event at [Venue] due to inability to implement basic security protocols. We are actively seeking alternative venues that prioritize the safety of all participants."
3. **Legal Documentation** of refusal for liability purposes
4. **Report to U.S. venues: DHS** for pattern tracking of non-compliant venues

---

## 4. Navigating Non-Compliant Venues

### When Venues Won't Cooperate with Framework

In the event a campus or building does not want to fork out the expenses, the onus is on the person doing these events and their security teams to implement ballistic clear shields effective immediately. The cost of life is more than appearances. 

**The Catholic Church has used this method to protect papal figures for ages now - it can work for you too.**

#### Portable Shield Implementation
- Ballistic shields should be modular or portable (e.g., lightweight polycarbonate panels) to ensure ease of use across multiple events, especially for speakers who travel frequently like Kirk did
- Security teams must receive training on deploying and maintaining ballistic shields to ensure proper setup and effectiveness during events
- Consider the "Popemobile" model - transparent protection that maintains visibility while ensuring safety

#### Public Communication Strategy
- Encourage organizers to publicly explain why ballistic shields are used (e.g., to protect free speech and prevent violence)
- This could counter perceptions that such measures make speakers seem distant or overly protected
- Frame it as protecting the audience's right to hear diverse viewpoints

#### Funding Alternative Solutions
Organizers can fund ballistic shields through:
- Crowdfunding campaigns specifically for security
- Sponsorships from free speech advocacy groups
- Partnerships with security firms
- Ticket surcharges explicitly marked for safety measures
- Direct donor contributions earmarked for protection

#### Legal Protection
- Include security clauses in all event contracts
- Venues must acknowledge liability for failing to meet basic security standards (e.g., vantage point control)
- Document all security requests and refusals for legal record
- Consider insurance policies that require minimum security standards

---

## 5. Implementation Guidelines

### 5.1 Immediate Actions (Within 48 Hours)

For events already scheduled:
- Deploy portable ballistic shields immediately
- Contract private security for vantage point control
- Implement enhanced perimeter screening
- Brief speakers on emergency extraction procedures

### 5.2 Funding Mechanisms

Organizations can fund enhanced security through:
- **Direct Allocation:** 15% of event budget minimum
- **Crowdfunding:** Transparent campaigns for security costs
- **Sponsorships:** Free speech advocacy groups
- **Insurance Requirement:** Security bonds for high-risk events
- **Government Grants:** U.S. venues: DHS/DOJ public safety programs

### 5.3 Training Requirements

All security personnel must complete:
- Ballistic barrier deployment certification
- Counter-sniper detection training
- Medical response/trauma care
- Crowd dynamics and extraction protocols
- De-escalation techniques

---

## 6. Adaptive Threat Response

### 6.1 Escalation Triggers

If initial security is breached, automatic escalation includes:
- Immediate speaker extraction
- Venue lockdown protocols
- Law enforcement surge response
- Aerial surveillance deployment

### 6.2 Technology Integration

- AI-powered threat detection systems
- Facial recognition for known threats
- Social media monitoring for threat indicators
- Encrypted communications mandatory

### 6.3 Post-Event Analysis

Every event requires:
- Security debrief within 24 hours
- Threat evolution assessment
- Protocol refinement recommendations
- Information sharing with other organizations

---

## 7. Long-Term Sustainability

### 7.1 Industry Standards

Push for adoption as:
- Insurance requirement for event coverage
- Venue licensing condition
- Professional security certification standard
- Federal guidelines for public events

### 7.2 Cost-Benefit Analysis

- **One-time barrier investment:** $15,000-50,000
- **Per-event security enhancement:** $5,000-25,000
- **Cost of single casualty:** Immeasurable
- **ROI:** Life saved = infinite return

### 7.3 Cultural Normalization

- Explain barriers as "protecting free speech, not just speakers"
- Compare to airport security evolution post-9/11
- Emphasize non-partisan nature of safety
- Document success stories of threats deterred

---

## 8. Executive Summary

The Kirk Protocol v4.0 represents a comprehensive security framework born from tragedy but oriented toward prevention. Key innovations include:

1. **Dynamic threat assessment** beyond single-vector attacks
2. **Objective speaker classification** removing political bias
3. **Non-cooperation protocols** ensuring accountability
4. **Practical workarounds** when venues refuse to comply - following the papal protection model that has worked for decades
5. **Barrier height calculations** based on venue geometry
6. **Insider threat considerations** addressing all vectors

The assassination of Charlie Kirk proved that hope is not a security strategy. This framework transforms grief into action, providing a roadmap to protect those who dare to speak publicly in an increasingly dangerous world.

**The cost of implementation is measured in dollars. The cost of inaction is measured in blood.**

---

## Appendices

### Appendix A: Emergency Contact Protocol
[To be developed by/with local law enforcement]

### Appendix B: Vendor List for Ballistic Materials
[Online sources available, contact the manufacturer for bespoke instalments.]

### Appendix C: Legal Templates for Venue Agreements
[Requires legal review by jurisdiction, get lawyers to make it]

### Appendix D: Training Curriculum Outline
[Security companies should be reviewing this]

---

*Version 4.0 - September 2025*
*In memory of Charlie Kirk (1993-2025)*
*"Free societies cannot survive when ideas are met with bullets instead of arguments."*

### Threat-to-Standard Map (specify these in procurement)
- **Handguns (9×19, .357, .44 Mag):** NIJ IIIA or UL 752 L1–L3 (glazing/walls). *Not rifle-rated.*
- **Intermediate rifles (5.56 NATO, 7.62×39):** NIJ III; UL 752 L7 (glazing).
- **Battle rifles (7.62×51 NATO M80 ball):** NIJ III; UL 752 L8 (glazing).
- **Armor‑piercing rifle (.30‑06 M2 AP):** NIJ IV (single hit by standard).  
  For facility products, require manufacturer certification naming **round, velocity, hit count and spacing**.
- **Beyond NIJ IV (.338 LM, multi‑hit AP, .50 BMG):** Not covered by NIJ IV. Require product‑specific test reports explicitly naming the threat and test protocol.
