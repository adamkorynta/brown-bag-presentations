---
marp: true
theme: default
paginate: true
size: 16:9
title: Agent Skills for Claude Code and Codex
description: Brown bag deck explaining how agent skills package procedural knowledge for Claude Code and Codex.
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
  font-size: 40px;
  line-height: 1.05;
  font-weight: 800;
  letter-spacing: 0;
  margin: 0 0 26px 0;
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

code {
  color: var(--gei-teal);
  font-family: "Cascadia Code", Consolas, monospace;
  font-size: 0.9em;
}

pre {
  background: #f7f8f4;
  border-left: 9px solid var(--gei-blue);
  padding: 16px 20px;
  margin: 0;
}

pre code {
  font-size: 20px;
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

.hero h1 { color: var(--gei-teal); max-width: 880px; }
.hero::after { background: var(--gei-teal); color: white; }

.subtitle {
  color: var(--gei-gray);
  font-size: 31px;
  line-height: 1.22;
  max-width: 790px;
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
  align-items: start;
}

.wide-left { grid-template-columns: 1.12fr 0.88fr; }
.wide-right { grid-template-columns: 0.88fr 1.12fr; }

.three-col {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  align-items: start;
}

.panel {
  border-left: 9px solid var(--gei-blue);
  padding: 18px 22px;
  background: #f5f6f2;
}

.panel.red { border-left-color: var(--gei-red); }
.panel.gold { border-left-color: var(--gei-gold); }
.panel.olive { border-left-color: var(--gei-olive); }

.panel p,
.panel li { font-size: 21px; }

.callout {
  font-size: 34px;
  line-height: 1.14;
  color: var(--gei-teal);
  font-weight: 800;
  border-left: 12px solid var(--gei-red);
  padding: 18px 24px;
  background: #f5f6f2;
}

.big {
  font-size: 64px;
  line-height: 1.02;
  font-weight: 800;
  color: var(--gei-teal);
}

.compact p,
.compact li {
  font-size: 21px;
  line-height: 1.16;
}

.compact h2 { font-size: 36px; margin-bottom: 20px; }
.compact h3 { font-size: 24px; margin-bottom: 8px; }

.tag-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 14px;
}

.tag {
  min-height: 64px;
  display: flex;
  align-items: center;
  background: #f5f6f2;
  border-top: 7px solid var(--gei-blue);
  color: var(--gei-teal);
  font-size: 22px;
  font-weight: 800;
  line-height: 1.08;
  padding: 12px 14px;
}

.tag:nth-child(2) { border-top-color: var(--gei-olive); }
.tag:nth-child(3) { border-top-color: var(--gei-gold); }
.tag:nth-child(4) { border-top-color: var(--gei-red); }

.compare {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 28px;
}

.compare .panel {
  min-height: 330px;
}

.memory-grid {
  display: grid;
  grid-template-columns: 0.9fr 1.1fr;
  gap: 22px;
  align-items: start;
}
</style>

<!-- _class: hero -->

# Agent Skills

<div class="subtitle">How Claude Code and Codex package procedural knowledge for repeatable agent work</div>

<div class="subtitle" style="margin-top: 34px;">A 15-minute technical framing deck</div>

<!--
Speaker notes:
Set the scope clearly. This talk focuses on skills as reusable procedures for agents, especially Claude Code and Codex. It is not a general prompt-engineering talk.
Sources: Anthropic Agent Skills overview, https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview. Claude Code plugin docs, https://code.claude.com/docs/en/plugins. OpenAI Developers homepage, https://developers.openai.com/. OpenAI Skills API reference, https://developers.openai.com/api/reference/python/resources/skills/methods/create.
-->

---

<div class="section-label">Concept</div>

## What a Skill Is

<div class="split wide-left">
  <div>
    <div class="big">A skill is a procedure the agent can load when the task calls for it.</div>
  </div>
  <div class="panel olive">
    <h3>Use skills for</h3>
    <ul>
      <li>Repeatable workflows</li>
      <li>Domain-specific process steps</li>
      <li>Reusable scripts and templates</li>
      <li>Tool usage patterns that need judgment</li>
    </ul>
  </div>
</div>

<div class="callout" style="margin-top: 34px;">Skills give an agent operating procedure without retraining the model.</div>

<!--
Speaker notes:
Keep the contrast practical: a skill is not the tool itself and not just a document. It is the instruction layer that tells the agent how to do a kind of work, with optional files and scripts alongside it.
Sources: Anthropic describes Skills as directories with instructions, scripts, and resources that Claude loads progressively. OpenAI describes plugins as extending Codex and ChatGPT with skills, MCP servers, and optional UI.
-->

---

<div class="section-label">Creation</div>

## Structure of a Skill

<div class="split wide-right">
  <div class="panel gold">
    <h3>Minimum useful skill</h3>
    <ul>
      <li><code>SKILL.md</code> at the skill root</li>
      <li>YAML front matter</li>
      <li>Clear trigger description</li>
      <li>Short procedural instructions</li>
    </ul>
  </div>
  <div>

```text
my-skill/
  SKILL.md
  references/
    decision-rules.md
  scripts/
    validate-inputs.js
  templates/
    report.md
```

```text
SKILL.md
  front matter:
    name: my-skill
    description: Use when...

  instructions:
    1. Inspect the inputs.
    2. Read only the needed references.
    3. Run the validator.
```

  </div>
</div>

<!--
Speaker notes:
The important point is that the structure supports staged loading. The agent sees enough metadata to decide the skill may apply, then reads the instructions, then reads supporting files only if the instructions call for them.
Sources: Anthropic Agent Skills overview, https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview. Claude Code plugin reference, https://code.claude.com/docs/en/plugins-reference.
-->

---

<!-- _class: compact -->

<div class="section-label">Specification</div>

## Common Skill Specification

<div class="three-col">
  <div class="panel">
    <h3>Front matter</h3>
    <p><code>name</code> and <code>description</code> identify the skill and tell the agent when to load it. Some runtimes add fields for tool restrictions or invocation behavior.</p>
  </div>
  <div class="panel olive">
    <h3>Directory structure</h3>
    <p><code>SKILL.md</code> holds the main procedure. Supporting folders hold references, scripts, templates, examples, or assets.</p>
  </div>
  <div class="panel gold">
    <h3>Progressive disclosure</h3>
    <p>The agent starts with metadata, loads instructions only when relevant, then opens extra files only as needed.</p>
  </div>
</div>

<div class="callout" style="margin-top: 30px;">The best skills keep the always-loaded part small and move detail into referenced files.</div>

<!--
Speaker notes:
Anthropic documents this as three levels: metadata always loaded, instructions loaded when the skill triggers, and resources or scripts loaded as needed. This is also the pattern Codex skills follow in practice: the description routes the work, and the body points to the files that matter.
Sources: Anthropic Agent Skills overview, https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview. Claude Code plugin docs, https://code.claude.com/docs/en/plugins.
-->

---

<!-- _class: compact -->

<div class="section-label">Installation</div>

## Where Skills Can Live

<div class="compare">
  <div class="panel">
    <h3>Claude Code</h3>
    <ul>
      <li>Personal: <code>~/.claude/skills/</code></li>
      <li>Project: <code>.claude/skills/</code></li>
      <li>Plugin: <code>skills/&lt;name&gt;/SKILL.md</code> inside a Claude Code plugin</li>
      <li>Marketplace installs can target user, project, or local scope</li>
    </ul>
  </div>
  <div class="panel olive">
    <h3>Codex and OpenAI agents</h3>
    <ul>
      <li>Personal Codex skills under <code>$CODEX_HOME/skills</code></li>
      <li>Plugin-bundled skills loaded with installed Codex plugins</li>
      <li>OpenAI API skills uploaded as files or zip archives</li>
      <li>Hosted agent environments can reference skill IDs or inline skill archives</li>
    </ul>
  </div>
</div>

<!--
Speaker notes:
For Claude Code, the documented filesystem paths are personal ~/.claude/skills and project .claude/skills, plus plugin skills. For Codex, the local app loads personal and plugin-provided skills, while the OpenAI API exposes first-class skill creation, versions, and hosted environment attachment.
Sources: Anthropic Agent Skills overview, https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview. Claude Code plugin docs, https://code.claude.com/docs/en/plugins. OpenAI Skills API, https://developers.openai.com/api/reference/python/resources/skills/methods/create. OpenAI hosted environment template API, https://developers.openai.com/api/reference/go/resources/beta/subresources/agents/subresources/environments/subresources/templates/methods/create.
-->

---

<!-- _class: compact -->

<div class="section-label">Repo guidance</div>

## AGENTS.md or Skill

<div class="split">
  <div class="panel gold">
    <h3>Use <code>AGENTS.md</code> for repository norms</h3>
    <ul>
      <li>How to run tests and builds</li>
      <li>Project architecture notes</li>
      <li>Style conventions</li>
      <li>Safety rules for this codebase</li>
      <li>Paths and commands every agent should know</li>
    </ul>
  </div>
  <div class="panel olive">
    <h3>Use a skill for reusable procedures</h3>
    <ul>
      <li>Workflows that travel across repos</li>
      <li>Steps with supporting references or templates</li>
      <li>Processes that benefit from scripts</li>
      <li>Instructions that should trigger only for specific tasks</li>
      <li>Team practices worth versioning as a capability</li>
    </ul>
  </div>
</div>

<div class="callout" style="margin-top: 24px;">A good rule: repo context goes in <code>AGENTS.md</code>; repeatable know-how becomes a skill.</div>

<!--
Speaker notes:
Make this decision feel concrete. AGENTS.md is the standing orientation for a repository. Skills are task-triggered capabilities. If the same process would help in three repositories, it probably wants to become a skill.
Source: OpenAI model guidance notes that models can be sensitive to instructions contained in skills and AGENTS.md, and recommends auditing files that influence model behavior: https://developers.openai.com/api/docs/guides/latest-model.
-->

---

<!-- _class: compact -->

<div class="section-label">Knowledge</div>

## How Agent Knowledge Works

<div class="tag-grid">
  <div class="tag">MCP gives the agent tool access</div>
  <div class="tag">RAG gives the agent factual knowledge</div>
  <div class="tag">Fine tuning changes model behavior in the weights</div>
  <div class="tag">Skills give the agent procedural knowledge</div>
</div>

<div class="callout" style="margin-top: 34px;">Pick the mechanism based on what the agent lacks: access, facts, learned behavior, or procedure.</div>

<!--
Speaker notes:
Use this as the mental model slide. MCP connects the agent to systems and tools. RAG retrieves factual context at run time. Fine tuning changes how the model behaves statistically. Skills encode how to do a kind of work, including when to fetch references or run scripts.
Sources: Anthropic plugin docs list MCP servers as plugin components alongside skills. OpenAI Developers describes plugins as extending ChatGPT and Codex with skills, MCP servers, and optional UI.
-->

---

<!-- _class: compact -->

<div class="section-label">Memory</div>

## Agent Memory

<div class="memory-grid">
  <div class="panel red">
    <h3>Memory answers one question</h3>
    <p>What should the agent carry forward after the current context window moves on?</p>
  </div>
  <div class="panel">
    <h3>Three useful types</h3>
    <ul>
      <li><strong>Semantic memory:</strong> durable facts retrieved through RAG or a memory store.</li>
      <li><strong>Episodic memory:</strong> conversation history, task logs, decisions, and prior attempts.</li>
      <li><strong>Procedural memory:</strong> skills that preserve how to perform a repeatable process.</li>
    </ul>
  </div>
</div>

<div class="callout" style="margin-top: 30px;">Skills are the agent memory you can review, version, test, and share.</div>

<!--
Speaker notes:
This taxonomy is a useful teaching model, not a claim that every product exposes memory with these exact labels. The key point is that skills are procedural memory: they preserve steps, judgment, references, templates, and scripts.
Source for hosted agent memory endpoints: Anthropic managed agents skills page mentions memory store endpoints and beta headers, https://platform.claude.com/docs/en/managed-agents/skills.
-->

---

<!-- _class: compact -->

<div class="section-label">Example</div>

## Archify: a Skill in Practice

<div class="callout" style="margin-bottom: 26px;">Archify starts from repository evidence and a typed diagram specification. It validates the result, then delivers a self-contained interactive viewer.</div>

<div class="three-col">
  <div class="panel">
    <h3><a href="https://adamkorynta.github.io/brown-bag-presentations/architecture/regi-headless-architecture.html">REGI Headless</a></h3>
    <p>Runtime architecture</p>
  </div>
  <div class="panel olive">
    <h3><a href="https://adamkorynta.github.io/brown-bag-presentations/architecture/mcwra-firo-dts-architecture.html">MCWRA FIRO DTS</a></h3>
    <p>Runtime architecture</p>
  </div>
  <div class="panel gold">
    <h3><a href="https://adamkorynta.github.io/brown-bag-presentations/architecture/ressim-compute-runtime.html">HEC-ResSim</a></h3>
    <p>Compute runtime architecture</p>
  </div>
</div>

<p style="margin-top: 28px;"><strong>Open any title for the live diagram.</strong> The viewer supports search, focus, relationship tracing, theme switching, and export.</p>

<!--
Speaker notes:
Open one example for a short live demo. Explain that Archify inspected the relevant repository, represented the architecture in a typed specification, checked the diagram, and delivered the standalone HTML viewer. The links point to copies of the user-supplied artifacts published with this deck.
Archify viewer capabilities and delivery workflow: local Archify skill documentation, version 2.17.
-->

---

<div class="section-label">Authoring</div>

## Skill Creation Should Use Skills

<div class="split wide-left">
  <div class="callout">
    Agent platforms now include skill-building skills. Use them instead of hand-rolling <code>SKILL.md</code> files from scratch.
  </div>
  <div class="panel olive">
    <h3>Why it matters</h3>
    <ul>
      <li>They enforce the expected format</li>
      <li>They keep progressive disclosure intact</li>
      <li>They separate instructions, references, scripts, and assets</li>
      <li>They reduce vague triggers and bloated skill bodies</li>
      <li>They help test whether the skill activates at the right time</li>
    </ul>
  </div>
</div>

<div class="panel gold" style="margin-top: 30px;">
  <h3>Practical recommendation</h3>
  <p>Describe the workflow in plain language, give the skill-creator the source materials, then review the generated skill like code.</p>
</div>

<!--
Speaker notes:
For this audience, make the recommendation strong: do not create skills by hand unless you are debugging the generated output. Codex has a skill-creator skill in this environment, and Claude Code can use skill and plugin workflows to scaffold reusable capabilities. Human review still matters.
Sources: Claude Code plugin docs describe plugin and skill creation workflows. OpenAI model guidance references Codex skills such as OpenAI Docs being reusable in other coding agents.
-->
