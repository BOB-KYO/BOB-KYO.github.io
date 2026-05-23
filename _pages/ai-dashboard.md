---
layout: single
title: "AI Agent Dashboard"
permalink: /ai-dashboard/
author_profile: true
toc: false
---

<style>
/* ── Dashboard Base ─────────────────────────────────────── */
.dash-section        { margin-bottom: 2.5rem; }
.dash-section h2     { border-bottom: 2px solid #e0e0e0; padding-bottom: .4rem; margin-bottom: 1.2rem; font-size: 1.2rem; }

/* ── Status Badges ──────────────────────────────────────── */
.badge               { display: inline-block; padding: .18em .65em; border-radius: 1em; font-size: .75rem; font-weight: 600; letter-spacing: .03em; vertical-align: middle; }
.badge-active        { background: #d4edda; color: #155724; }
.badge-registered    { background: #d1ecf1; color: #0c5460; }
.badge-pending       { background: #fff3cd; color: #856404; }
.badge-primary       { background: #cce5ff; color: #004085; }
.badge-specialist    { background: #e2e3e5; color: #383d41; }
.badge-runtime       { background: #f8d7da; color: #721c24; }
.badge-completed     { background: #d4edda; color: #155724; }

/* ── Agent Cards ────────────────────────────────────────── */
.agent-grid          { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1rem; }
.agent-card          { border: 1px solid #dee2e6; border-radius: 10px; padding: 1rem 1.1rem; background: #fff; transition: box-shadow .15s; }
.agent-card:hover    { box-shadow: 0 2px 10px rgba(0,0,0,.1); }
.agent-card.primary  { border-left: 4px solid #0d6efd; }
.agent-card.runtime  { border-left: 4px solid #dc3545; }
.agent-card.specialist { border-left: 4px solid #6c757d; }
.agent-name          { font-weight: 700; font-size: 1rem; margin-bottom: .25rem; }
.agent-model         { font-size: .78rem; color: #6c757d; margin-bottom: .4rem; font-family: monospace; }
.agent-desc          { font-size: .83rem; color: #495057; margin-top: .5rem; line-height: 1.4; }

/* ── Infrastructure Table ───────────────────────────────── */
.infra-table         { width: 100%; border-collapse: collapse; font-size: .85rem; }
.infra-table th      { background: #f8f9fa; padding: .5rem .75rem; text-align: left; border-bottom: 2px solid #dee2e6; }
.infra-table td      { padding: .45rem .75rem; border-bottom: 1px solid #f0f0f0; vertical-align: top; }
.infra-table tr:hover td { background: #f9f9f9; }
.code-sm             { font-family: monospace; font-size: .78rem; background: #f4f4f4; padding: .1em .4em; border-radius: 4px; }

/* ── Seed Log ───────────────────────────────────────────── */
.seed-log            { border: 1px solid #dee2e6; border-radius: 8px; overflow: hidden; }
.seed-row            { display: grid; grid-template-columns: 1fr 2.5fr 1fr 1fr; align-items: center; padding: .55rem 1rem; gap: .75rem; border-bottom: 1px solid #f0f0f0; font-size: .83rem; }
.seed-row:last-child { border-bottom: none; }
.seed-row.header     { background: #f8f9fa; font-weight: 600; font-size: .8rem; color: #495057; }
.seed-id             { font-family: monospace; }

/* ── Four Principles ────────────────────────────────────── */
.principles          { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: .8rem; }
.principle-card      { border: 1px solid #dee2e6; border-radius: 8px; padding: .85rem 1rem; background: #fafafa; }
.principle-num       { font-size: 1.6rem; font-weight: 800; color: #dee2e6; float: right; line-height: 1; }
.principle-title     { font-weight: 700; font-size: .9rem; margin-bottom: .3rem; }
.principle-body      { font-size: .8rem; color: #666; line-height: 1.4; }
</style>

<p style="color:#6c757d; font-size:.85rem;">
  Last updated: <strong>2026-05-23</strong> &nbsp;·&nbsp;
  System: <strong>Windows 11 / WSL Ubuntu-22.04</strong> &nbsp;·&nbsp;
  Workspace: <span class="code-sm">D:\AIothch\</span>
</p>

---

<div class="dash-section">
<h2>🤖 Active Agents</h2>

<div class="agent-grid">

{% for agent in site.data.ai_agents.agents %}
{% if agent.status == "active" %}
<div class="agent-card {{ agent.type }}">
  <div class="agent-name">{{ agent.name }}</div>
  {% if agent.model %}<div class="agent-model">{{ agent.model }}</div>{% endif %}
  <div>
    <span class="badge badge-{{ agent.status }}">{{ agent.status }}</span>
    <span class="badge badge-{{ agent.type }}">{{ agent.type }}</span>
  </div>
  <div class="agent-desc">{{ agent.description }}</div>
  {% if agent.worktree %}
  <div style="margin-top:.5rem; font-size:.78rem; color:#888;">
    📁 <span class="code-sm">{{ agent.worktree }}</span>
    {% if agent.branch %}&nbsp;·&nbsp;<span class="code-sm">{{ agent.branch }}</span>{% endif %}
  </div>
  {% endif %}
</div>
{% endif %}
{% endfor %}

</div>
</div>

---

<div class="dash-section">
<h2>🛠 Specialist Agents (16 registered)</h2>

<div class="agent-grid">

{% for agent in site.data.ai_agents.agents %}
{% if agent.status == "registered" %}
<div class="agent-card specialist">
  <div class="agent-name">{{ agent.name }}</div>
  <div>
    <span class="badge badge-registered">registered</span>
    <span class="badge badge-specialist">specialist</span>
  </div>
  <div class="agent-desc">{{ agent.description }}</div>
</div>
{% endif %}
{% endfor %}

</div>
</div>

---

<div class="dash-section">
<h2>🏗 Infrastructure</h2>

<table class="infra-table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    {% for item in site.data.ai_agents.infrastructure %}
    <tr>
      <td>
        <strong>{{ item.name }}</strong>
        {% if item.url %}
        <br><a href="{{ item.url }}" target="_blank" style="font-size:.78rem;">{{ item.url }}</a>
        {% endif %}
      </td>
      <td><span class="badge badge-primary">{{ item.type }}</span></td>
      <td>{{ item.description }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

</div>

---

<div class="dash-section">
<h2>🌱 Ouroboros Seed Log</h2>

<div class="seed-log">
  <div class="seed-row header">
    <span>Seed ID</span>
    <span>Goal</span>
    <span>Date</span>
    <span>Result</span>
  </div>
  {% for seed in site.data.ai_agents.seeds %}
  <div class="seed-row">
    <span class="seed-id">{{ seed.id }}</span>
    <span>{{ seed.goal }} <span style="color:#aaa;font-size:.75rem;">({{ seed.ac_completed }}/{{ seed.ac_total }} ACs · {{ seed.parallelism }})</span></span>
    <span>{{ seed.date }}</span>
    <span><span class="badge badge-{{ seed.status }}">{{ seed.status }}</span></span>
  </div>
  {% endfor %}
</div>

</div>

---

<div class="dash-section">
<h2>📐 4 Principles (Governance)</h2>

<div class="principles">

<div class="principle-card">
  <span class="principle-num">1</span>
  <div class="principle-title">No Code Without Packet</div>
  <div class="principle-body">50_packet (Obsidian approval) required before any code change. No exceptions.</div>
</div>

<div class="principle-card">
  <span class="principle-num">2</span>
  <div class="principle-title">Scope Lock</div>
  <div class="principle-body">Agents work only within packet-defined <code>allowed_paths</code>. <code>forbidden_paths</code>: absolute block.</div>
</div>

<div class="principle-card">
  <span class="principle-num">3</span>
  <div class="principle-title">Plan Mode Authority</div>
  <div class="principle-body">Claude Code plan mode decides when/whether Ouroboros is invoked. Autonomous calls blocked.</div>
</div>

<div class="principle-card">
  <span class="principle-num">4</span>
  <div class="principle-title">Obsidian SSOT</div>
  <div class="principle-body"><code>60_사용자채택_결정기록/</code> is the single source of truth. Session logs are evidence only.</div>
</div>

</div>
</div>

---

<div class="dash-section">
<h2>🔗 Quick Links</h2>

| Resource | Link |
|---|---|
| GitHub (ai-control) | [BOB-KYO/ai-control](https://github.com/BOB-KYO/ai-control) *(private)* |
| GitHub (my-app) | [BOB-KYO/my-app](https://github.com/BOB-KYO/my-app) *(private)* |
| Portfolio | [GitHub Pages](https://bob-kyo.github.io) |
| Ouroboros | [pypi.org/ouroboros-ai](https://pypi.org/project/ouroboros-ai/) |

</div>

<p style="font-size:.75rem; color:#aaa; margin-top:2rem; text-align:right;">
  Data source: <code>_data/ai_agents.yml</code> &nbsp;·&nbsp; 
  Built with Jekyll on GitHub Pages
</p>
