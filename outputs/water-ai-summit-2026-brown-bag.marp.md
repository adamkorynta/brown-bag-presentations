---
marp: true
theme: default
paginate: true
size: 16:9
title: Water AI Summit 2026 Brown Bag
description: Brown bag discussion deck on AI in water utilities, decision support, trust, and operational value.
---

<style>
:root {
  --gei-teal: #003e53;
  --gei-deep: #011820;
  --gei-blue: #0087a9;
  --gei-red: #d3002d;
  --gei-gold: #ecb83c;
  --gei-olive: #aab921;
  --gei-gray: #656465;
  --gei-paper: #e3e3db;
  font-family: "Source Sans Pro", "Segoe UI", Arial, sans-serif;
}

section {
  width: 1280px;
  height: 720px;
  padding: 58px 76px 54px 82px;
  color: var(--gei-deep);
  background-color: #ffffff !important;
  background:
    linear-gradient(90deg, var(--gei-red) 0 11px, transparent 11px),
    linear-gradient(180deg, transparent 0 665px, var(--gei-gold) 665px 671px, transparent 671px),
    linear-gradient(#ffffff, #ffffff) !important;
}

section::after {
  color: white;
  background: var(--gei-teal);
  min-width: 42px;
  height: 28px;
  padding: 2px 8px;
  right: 54px;
  bottom: 24px;
  font-size: 17px;
  font-weight: 700;
  text-align: center;
}

h1 {
  color: var(--gei-teal);
  font-size: 54px;
  line-height: 0.98;
  font-weight: 800;
  letter-spacing: 0;
  margin: 0 0 18px 0;
}

h2 {
  color: var(--gei-teal);
  font-size: 40px;
  line-height: 1.05;
  font-weight: 800;
  letter-spacing: 0;
  margin: 0 0 28px 0;
}

h3 {
  color: var(--gei-teal);
  font-size: 27px;
  margin: 0 0 12px 0;
}

p, li {
  font-size: 24px;
  line-height: 1.22;
}

ul, ol { margin-top: 12px; }

strong { color: var(--gei-teal); }

blockquote {
  border-left: 12px solid var(--gei-red);
  padding: 14px 24px;
  background: #f5f6f2;
  color: var(--gei-teal);
  font-size: 31px;
  font-weight: 800;
  line-height: 1.15;
  margin: 24px 0;
}

blockquote p {
  font-size: inherit;
  line-height: inherit;
}

code {
  color: var(--gei-teal);
  font-family: "Cascadia Code", Consolas, monospace;
  font-size: 22px;
}

pre {
  background: #f7f8f4;
  border-left: 9px solid var(--gei-blue);
  padding: 18px 22px;
}

pre code {
  font-size: 24px;
  line-height: 1.12;
}

.hero {
  color: var(--gei-deep);
  background-color: #ffffff !important;
  background:
    radial-gradient(circle at 82% 24%, rgba(0,135,169,0.14) 0 96px, transparent 97px),
    radial-gradient(circle at 88% 34%, rgba(236,184,60,0.24) 0 70px, transparent 71px),
    linear-gradient(90deg, var(--gei-red) 0 14px, transparent 14px),
    linear-gradient(180deg, #ffffff 0%, #f5f6f2 100%) !important;
}

.hero h1 {
  color: var(--gei-teal);
  font-size: 58px;
  max-width: 820px;
}

.hero h2 {
  color: var(--gei-gray);
  font-size: 31px;
  line-height: 1.22;
  font-weight: 600;
  max-width: 760px;
}

.hero::after { background: var(--gei-teal); color: white; }

.subtitle {
  color: var(--gei-gray);
  font-size: 31px;
  line-height: 1.22;
  max-width: 760px;
}

.section-label {
  position: absolute;
  top: 24px;
  right: 74px;
  color: var(--gei-gray);
  font-size: 15px;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 1.4px;
}

.split,
.two-col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 42px;
  align-items: start;
}

.three-col {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 28px;
  align-items: start;
}

.small p,
.small li { font-size: 20px; }
.small h2 { font-size: 32px; }
.small h3 { font-size: 24px; }

.big {
  font-size: 66px;
  line-height: 1.02;
  font-weight: 800;
  color: var(--gei-teal);
}

.callout {
  font-size: 34px;
  line-height: 1.14;
  color: var(--gei-teal);
  font-weight: 800;
  border-left: 12px solid var(--gei-red);
  padding: 18px 24px;
  background: #f5f6f2;
}

.panel {
  border-left: 9px solid var(--gei-blue);
  padding: 20px 24px;
  background: #f5f6f2;
}

.panel.red { border-left-color: var(--gei-red); }
.panel.gold { border-left-color: var(--gei-gold); }
.panel.olive { border-left-color: var(--gei-olive); }

.tag {
  display: inline-block;
  color: var(--gei-teal);
  background: #f5f6f2;
  border-top: 5px solid var(--gei-blue);
  padding: 8px 13px;
  font-size: 20px;
  font-weight: 800;
  margin: 5px 8px 5px 0;
}

.tag:nth-of-type(3n + 1) { border-top-color: var(--gei-blue); }
.tag:nth-of-type(3n + 2) { border-top-color: var(--gei-gold); }
.tag:nth-of-type(3n) { border-top-color: var(--gei-olive); }

.compact h1 {
  font-size: 48px;
  margin-bottom: 14px;
}

.compact p,
.compact li {
  font-size: 21px;
  line-height: 1.14;
}

.compact blockquote {
  font-size: 25px;
  line-height: 1.08;
  margin: 16px 0 0 0;
  padding: 12px 20px;
}

.compact pre {
  margin: 0;
  padding: 14px 18px;
}

.compact pre code {
  font-size: 19px;
  line-height: 1.02;
}

.tag-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin: 14px 0 18px 0;
}

.tag-grid .tag {
  display: flex;
  align-items: center;
  min-height: 46px;
  margin: 0;
  padding: 8px 12px;
  font-size: 18px;
  line-height: 1.05;
}

.compact-stack {
  display: grid;
  gap: 16px;
}

.compact-split {
  display: grid;
  grid-template-columns: 1.12fr 0.88fr;
  gap: 28px;
  align-items: start;
}

.compact-panel {
  background: #f5f6f2;
  border-left: 9px solid var(--gei-blue);
  padding: 16px 20px;
}

.compact-panel h3 {
  font-size: 24px;
  margin-bottom: 8px;
}

.compact-panel ul {
  margin: 0;
  padding-left: 24px;
}

.compact-panel li {
  margin: 5px 0;
}

.compact-panel .tag {
  display: block;
  margin: 0 0 8px 0;
  font-size: 18px;
  line-height: 1.05;
}

.tag-list-two {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.tag-list-two h3 {
  grid-column: 1 / -1;
}

.tag-list-two .tag {
  display: flex;
  align-items: center;
  min-height: 50px;
  margin: 0;
}

.tag-grid-two {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-top: 12px;
}

.compact-panel .tag-grid-two .tag {
  display: flex;
  align-items: center;
  min-height: 48px;
  margin: 0;
  padding: 8px 12px;
}

.takeaways {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.takeaway {
  min-height: 146px;
  background: #f5f6f2;
  padding: 22px;
  border-top: 9px solid var(--gei-blue);
}

.takeaway:nth-child(2) { border-top-color: var(--gei-olive); }
.takeaway:nth-child(3) { border-top-color: var(--gei-gold); }
.takeaway:nth-child(4) { border-top-color: var(--gei-red); }

.takeaway p {
  font-size: 22px;
  margin: 0;
}
</style>

<!-- _class: hero -->
# Water AI Summit 2026
## What actually matters for AI in water utilities

**Brown bag discussion**  
Adam Korynta - Davis / RMA / GEI

<!--
Opening: I expected more ChatGPT hype. The actual through-line was decision support, data integration, validation, and governance.
-->

---

# Presentations covered a wide range

<div class="three-col small">

<div>

### Utilities
- ReWa
- Valley Water
- UMngeni-uThukela Water

</div>

<div>

### Vendors & consultants
- Bentley
- Inframark
- Kamstrup
- SEW.AI
- STV
- Freese and Nichols
- Hammond Power Solutions

</div>

<div>

### Security & governance
- Agilicus
- Venable
- Camelot Investigations
- Cybersecurity panel

</div>

</div>

<!--
Mention that the same themes appeared across very different organizations and use cases.
-->

---

# Theme 1: AI is not the product

Common refrains:

- **Prediction is not a decision**
- **Visibility is not action**
- **AI does not create value by itself**
- **Start with the problem, not the AI**

Utilities are not buying AI. They are buying fewer surprises, lower costs, safer operations, and better planning.

---

# The actual value chain

```text
Data
  + Context
    -> Insight
      + Expected Value
        -> Prediction
          + Risk Assessment
            -> Intelligence
              + Human Judgment
                -> Decision
```

<div class="callout">
AI is one layer in a decision workflow, not the workflow itself.
</div>

<!--
This came from the Know Idea presentation and matched the rest of the conference.
-->

---

<!-- _class: compact -->

# Theme 2: Utilities have data, not context

Most utilities already have:

<div class="tag-grid">
<span class="tag">SCADA</span>
<span class="tag">Historians</span>
<span class="tag">GIS</span>
<span class="tag">Smart meters</span>
<span class="tag">Work orders</span>
<span class="tag">Asset data</span>
<span class="tag">Weather</span>
<span class="tag">Inspection records</span>
</div>

The hard part is connecting data across systems with consistent metadata, timestamps, asset identities, and operational meaning.

> The utility does not have a data shortage. It has a context and integration problem.

---

# Theme 3: Digital twins are not just 3D models

The conference used **digital twin** to mean:

> A continuously updated operational model of the real system.

<div class="two-col">

<div>

### Inputs
- Sensors
- SCADA
- GIS
- LiDAR
- Asset history
- Hydraulic models

</div>

<div>

### Uses
- Simulation
- Leak localization
- Rehab planning
- Cyber consequence analysis
- Predictive maintenance

</div>

</div>

<!--
Use Bentley, LiDAR, Valley Water/K-Water, pump health, and cyber digital twin examples.
-->

---

# Theme 4: Explainability is not optional

AI recommendations need to show:

- Source data
- Relevant documents
- Confidence / uncertainty
- Why the score changed
- What asset or process is affected
- Audit trail back to supporting evidence

This matters for capital planning, compliance, cyber incidents, and public-sector accountability.

---

# Theme 5: Human-in-the-loop was everywhere

<div class="two-col">

<div>

### AI should answer
- What happened?
- What changed?
- What is likely next?
- What evidence supports it?
- What options exist?

</div>

<div>

### Humans still decide
- Start / stop pumps
- Open / close valves
- Chemical dosing
- Maintenance priority
- Capital spending
- Emergency response

</div>

</div>

<div class="callout">
AI protects the decision. Humans control the process.
</div>

---

<!-- _class: compact -->

# Theme 6: Start small, validate, then scale

<div class="compact-split">

<div>

### Best pattern

```text
Pick one operational problem
  -> Use existing read-only data
    -> Establish a baseline
      -> Validate predictions
        -> Act and measure outcome
          -> Expand by basin, asset, or facility
```

</div>

<div class="compact-panel">

<h3>Good starting points</h3>

<div class="tag-grid-two">
<span class="tag">I&I</span>
<span class="tag">Pump health</span>
<span class="tag">Leak detection</span>
<span class="tag">Aeration</span>
<span class="tag">Chemical dosing</span>
<span class="tag">Transformer monitoring</span>
</div>

</div>

</div>

---

# Theme 7: Closed-loop learning

The mature pattern was not just **predict**.

```text
Predict -> Act -> Measure -> Feed back -> Improve
```

Examples:

- Smart meter anomaly confirmed by field crew
- Pump prediction checked against maintenance result
- Transformer model recalibrated after repair
- Rehab investment validated against basin performance

---

# Theme 8: Governance is catching up

Questions organizations now need to answer:

- Where is AI being used?
- What data can it access?
- Who approved the use case?
- How does it fail under stress or misuse?
- Can a human override it?
- What is the fallback procedure?

The NIST AI Risk Management Framework came up as a practical governance lens.

---

<!-- _class: compact -->

# Theme 9: Cybersecurity is part of AI adoption

<div class="compact-split">

<div class="compact-panel">

### The talks were blunt

- Air gaps are no longer enough
- VPNs are not enough
- OT needs identity-aware access
- Machine-to-machine traffic needs controls
- Sensitive operational data should stay in controlled environments

</div>

<div class="compact-panel">

<h3>Relevant concepts</h3>

<div class="tag-grid-two">
<span class="tag">Zero Trust</span>
<span class="tag">mTLS</span>
<span class="tag">Identity-aware proxy</span>
<span class="tag">Least privilege</span>
<span class="tag">Forensic vaulting</span>
<span class="tag">RAG in private tenant</span>
</div>

</div>

</div>

---

# Theme 10: People matter more than models

One useful formula:

> **AI Technology x AI Fluency = Operational Value**

Access to AI is no longer the differentiator.

The differentiator is whether people can:

- Ask better questions
- Apply domain knowledge
- Validate outputs
- Safeguard IP and PII
- Turn results into actual work

---

# What felt real vs. hype?

<div class="two-col small">

<div>

## Real now
- Report generation
- Natural language search over internal docs
- Leak prioritization
- Predictive maintenance
- Anomaly detection
- Data quality assistance
- Cyber alert correlation

</div>

<div>

## Still immature
- Fully autonomous operations
- One-system digital twins
- Agentic control of infrastructure
- Enterprise-wide AI without data cleanup
- Generic AI replacing domain workflows

</div>

</div>

---

# Why this matters for us

Our work already sits in the middle of the AI value chain:

- Enterprise integration
- Operational databases
- Forecasting systems
- External data pipelines
- Engineering workflows
- Decision-support tools
- Auditability and governance

AI does not reduce the need for that work. It increases the value of doing it well.

---

# Opportunities for our branch

Potential directions:

1. **RAG over trusted engineering documentation**  
   Manuals, SOPs, model documentation, release notes, project records.

2. **AI-assisted decision support**  
   Recommendations with source evidence, confidence, and human approval.

3. **Operational anomaly workflows**  
   Detection -> explanation -> work order / review -> feedback loop.

4. **Prepare operational data for AI**  
   Clean up metadata, trace where data came from, document how it changes over time, check quality, and connect systems so outputs can be trusted.

---

# Discussion prompts

- Where do our existing systems already provide the context AI needs?
- Which workflows would benefit most from explainable recommendations?
- What data would we trust enough to use in AI-assisted decisions?
- Where could we start small and validate value quickly?
- What governance would our clients expect before using AI outputs?
