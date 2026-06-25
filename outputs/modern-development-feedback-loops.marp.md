---
marp: true
theme: default
paginate: true
size: 16:9
title: Modern Development Feedback Loops
description: Condensed brown bag deck for Docker, hot reloading, and AI-assisted development.
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
  font-size: 58px;
  line-height: 0.98;
  font-weight: 800;
  letter-spacing: 0;
  margin: 0 0 18px 0;
}

h2 {
  color: var(--gei-teal);
  font-size: 42px;
  line-height: 1.05;
  font-weight: 800;
  letter-spacing: 0;
  margin: 0 0 28px 0;
}

h3 {
  color: var(--gei-teal);
  font-size: 28px;
  margin: 0 0 12px 0;
}

p, li {
  font-size: 25px;
  line-height: 1.22;
}

code {
  color: var(--gei-teal);
  font-family: "Cascadia Code", Consolas, monospace;
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

.hero h1 { color: var(--gei-teal); }
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

.split {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 42px;
  align-items: center;
}

.wide-left { grid-template-columns: 1.18fr 0.82fr; }
.wide-right { grid-template-columns: 0.82fr 1.18fr; }

.big {
  font-size: 66px;
  line-height: 1.02;
  font-weight: 800;
  color: var(--gei-teal);
}

.callout {
  font-size: 36px;
  line-height: 1.14;
  color: var(--gei-teal);
  font-weight: 800;
  border-left: 12px solid var(--gei-red);
  padding-left: 24px;
}

.panel {
  border-left: 9px solid var(--gei-blue);
  padding: 20px 24px;
  background: #f5f6f2;
}

.panel.red { border-left-color: var(--gei-red); }
.panel.gold { border-left-color: var(--gei-gold); }
.panel.olive { border-left-color: var(--gei-olive); }

.comparison {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 28px;
}

.compare-box {
  min-height: 290px;
  padding: 28px;
  border-top: 12px solid var(--gei-gray);
  background: #f3f4f0;
}

.compare-box.modern {
  border-top-color: var(--gei-olive);
  background: #f7f8ee;
}

.compare-label {
  font-size: 20px;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 1px;
  color: var(--gei-gray);
}

.metric {
  font-size: 78px;
  font-weight: 800;
  line-height: 0.95;
  color: var(--gei-red);
}

.modern .metric { color: var(--gei-olive); }

.flow {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 18px;
  margin-top: 40px;
}

.step {
  flex: 1;
  min-height: 108px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 16px;
  color: var(--gei-teal);
  background: #f5f6f2;
  border-top: 8px solid var(--gei-blue);
  font-size: 25px;
  font-weight: 800;
}

.step.wait { border-top-color: var(--gei-red); }
.step.fast { border-top-color: var(--gei-olive); }

.arrow {
  color: var(--gei-red);
  font-size: 38px;
  font-weight: 800;
}

.diagram {
  background: #f7f8f4;
  border-left: 9px solid var(--gei-blue);
  padding: 18px 22px;
}

.diagram pre {
  margin: 0;
  font-size: 18px;
  line-height: 1.05;
}

.node-row {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin: 14px 0;
}

.node-stack {
  display: grid;
  grid-template-columns: 1fr;
  gap: 14px;
  max-width: 360px;
  margin: 0 auto;
}

.node {
  min-height: 66px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 12px 14px;
  color: var(--gei-teal);
  background: white;
  border: 3px solid var(--gei-blue);
  font-size: 22px;
  font-weight: 800;
}

.node.accent { border-color: var(--gei-red); }
.node.good { border-color: var(--gei-olive); }
.node.gold { border-color: var(--gei-gold); }
.node.db { border-radius: 28px; }

.connector {
  color: var(--gei-red);
  font-size: 28px;
  font-weight: 800;
  min-width: 28px;
  text-align: center;
}

.compose-box {
  border: 4px solid var(--gei-teal);
  background: #ffffff;
  padding: 18px;
  margin-bottom: 16px;
}

.compose-label {
  color: var(--gei-teal);
  text-transform: uppercase;
  font-size: 16px;
  font-weight: 800;
  letter-spacing: 1px;
  margin-bottom: 12px;
}

.compact-diagram {
  padding: 14px 18px;
}

.compact-diagram .compose-box {
  padding: 12px;
  margin-bottom: 10px;
}

.compact-diagram .node-row {
  margin: 8px 0;
}

.compact-diagram .node {
  min-height: 52px;
  font-size: 20px;
  padding: 8px 12px;
}

.demo-panels {
  margin-top: 18px;
}

.demo-panels .panel {
  padding: 14px 18px;
}

.demo-panels h3 {
  font-size: 24px;
  margin-bottom: 6px;
}

.demo-panels p {
  font-size: 20px;
  margin: 0;
}

.compact-list {
  list-style: none;
  padding: 0;
  margin: 14px 0 0 0;
}

.compact-list li {
  margin: 13px 0;
  padding-left: 24px;
  border-left: 7px solid var(--gei-gold);
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

.caption {
  color: var(--gei-gray);
  font-size: 18px;
  line-height: 1.25;
}
</style>

<!-- _class: hero -->

# Modern Development Feedback Loops

<div class="subtitle">Docker, hot reloading, and AI-assisted development</div>

<div class="subtitle" style="margin-top: 34px;">10-12 minutes of framing, then the demo.</div>

<!--
Speaker notes:
Set the expectation immediately: this is a short framing talk, not a full tooling lecture. The goal is to make the live demo easier to interpret by explaining the feedback-loop idea first.
-->

---

<div class="section-label">Core idea</div>

<div class="big">Developer productivity is mostly feedback-loop speed.</div>

<div class="split" style="margin-top: 54px;">
  <div class="panel red">
    <h3>Slow loop</h3>
    <p>Write code, wait, lose context, debug the environment.</p>
  </div>
  <div class="panel olive">
    <h3>Fast loop</h3>
    <p>Make a change, see behavior, adjust while the idea is fresh.</p>
  </div>
</div>

<!--
Speaker notes:
Keep this slide punchy. The whole talk comes down to one practical claim: the faster a team can move from idea to observed behavior, the faster it can learn.
-->

---

<div class="section-label">Before and after</div>

## From Minutes to Seconds

<div class="comparison">
  <div class="compare-box">
    <div class="compare-label">Traditional</div>
    <div class="metric" style="margin-top: 34px;">Minutes</div>
    <p>Code -> build -> restart services -> test</p>
  </div>
  <div class="compare-box modern">
    <div class="compare-label">Modern</div>
    <div class="metric" style="margin-top: 34px;">Seconds</div>
    <p>Code -> save -> observe</p>
  </div>
</div>

<!--
Speaker notes:
This is the contrast that matters. In local development, "deploy" and "restart" often collapse into the same painful step: rebuild the app, restart one or more services, refresh state, and then test. Keep the language simple so the audience focuses on waiting versus learning.
-->

---

<div class="section-label">Docker</div>

## Containerized Development

<div class="split wide-left">
  <div class="diagram">
    <div class="node-row">
      <div class="node accent">Developer</div>
      <div class="connector">&rarr;</div>
      <div class="node gold">Docker Compose</div>
    </div>
    <div class="node-row">
      <div class="node good">Frontend</div>
      <div class="connector">&harr;</div>
      <div class="node">Backend API</div>
      <div class="connector">&harr;</div>
      <div class="node db">Database</div>
    </div>
  </div>
  <div>
    <div class="callout">The development environment becomes part of the source code.</div>
    <ul class="compact-list">
      <li>Same services</li>
      <li>Same versions</li>
      <li>Same startup path</li>
    </ul>
  </div>
</div>

<!--
Speaker notes:
Explain containers as a team interface. They reduce local setup friction and make the runtime environment reproducible for developers, CI, and AI agents.
-->

---

<div class="section-label">Hot reload</div>

## Hot Reloading

<div class="flow">
  <div class="step fast">Edit</div>
  <div class="arrow">&rarr;</div>
  <div class="step fast">Save</div>
  <div class="arrow">&rarr;</div>
  <div class="step fast">Reload</div>
  <div class="arrow">&rarr;</div>
  <div class="step fast">Validate</div>
</div>

<div class="split" style="margin-top: 54px;">
  <div class="panel olive">
    <h3>Frontend</h3>
    <p>Vite keeps UI changes near-instant.</p>
  </div>
  <div class="panel gold">
    <h3>Backend</h3>
    <p>.NET Hot Reload reduces restart drag.</p>
  </div>
</div>

<!--
Speaker notes:
Hot reload is the part people feel most directly. It turns saves into signals, which makes experimentation cheaper and keeps attention on product behavior instead of startup rituals.
-->

---

<div class="section-label">AI agents</div>

## AI Needs a Runnable Environment

<div class="split wide-right">
  <div class="panel red">
    <h3>Without a reproducible environment</h3>
    <p>AI can run commands, but failures may reflect local setup instead of the code change.</p>
  </div>
  <div class="diagram">
    <div class="node-row">
      <div class="node accent">AI agent</div>
      <div class="connector">&harr;</div>
      <div class="node">Source code</div>
      <div class="connector">&harr;</div>
      <div class="node gold">Docker environment</div>
    </div>
    <div class="node-row">
      <div class="node good">Running app</div>
      <div class="connector">&harr;</div>
      <div class="node">Logs, tests, browser</div>
    </div>
  </div>
</div>

<!--
Speaker notes:
Do not imply agents are unable to run commands. The grounded point is that command execution is only as useful as the environment behind it. Containers make the app startup path explicit, reproducible, and easier for both humans and agents to verify against.
-->

---

<div class="section-label">Demo setup</div>

## What the Demo Will Show

<div class="diagram compact-diagram">
  <div class="compose-box">
    <div class="compose-label">Docker Compose</div>
    <div class="node-row">
      <div class="node good">React / Vite</div>
      <div class="connector">&harr;</div>
      <div class="node">.NET API</div>
      <div class="connector">&harr;</div>
      <div class="node db">Database</div>
    </div>
  </div>
  <div class="node-row">
    <div class="node accent">Browser</div>
    <div class="connector">&harr;</div>
    <div class="node gold">AI coding agent</div>
  </div>
</div>

<div class="split demo-panels">
  <div class="panel olive"><h3>Goal</h3><p>Make a full stack change and see it running.</p></div>
  <div class="panel gold"><h3>Watch for</h3><p>Fast feedback, visible errors, quick correction.</p></div>
</div>

<!--
Speaker notes:
Use this slide to hand off into the live portion. Give people the mental model: React/Vite frontend, .NET API, database, all managed through Docker Compose. The demo is about the loop more than the specific feature.
-->

---

<div class="section-label">Live portion</div>

<div class="big" style="margin-top: 130px;">Demo</div>

<div class="callout" style="margin-top: 54px; max-width: 780px;">Now let's make a full stack change against the running app.</div>

<!--
Speaker notes:
Use this as a simple transition slide while switching to the terminal, editor, browser, or agent view. Keep the spoken setup brief and move into the demo.
-->

---

<div class="section-label">Close</div>

## Takeaways

<div class="takeaways">
  <div class="takeaway">
    <h3>Faster feedback</h3>
    <p>Smaller changes, less waiting, less context switching.</p>
  </div>
  <div class="takeaway">
    <h3>Simpler onboarding</h3>
    <p>One shared startup path beats scattered setup notes.</p>
  </div>
  <div class="takeaway">
    <h3>Better AI leverage</h3>
    <p>Agents improve when they can run and verify.</p>
  </div>
  <div class="takeaway">
    <h3>Java options exist</h3>
    <p>Spring Boot DevTools, Quarkus dev mode, JRebel, DCEVM + HotswapAgent.</p>
  </div>
</div>

<!--
Speaker notes:
Use this only after the demo or as a quick backup close if time gets tight. Acknowledge that the demo stack is web-oriented, but the feedback-loop principle applies in Java too. Spring Boot DevTools can restart apps quickly during development. Quarkus dev mode is designed around live coding. JRebel and DCEVM with HotswapAgent offer deeper class reloading options. For desktop applications, the answer may be a mix of JVM hot swap, faster integration tests, better test fixtures, scripted startup, and isolating UI changes so the whole app does not need a full restart.
-->
