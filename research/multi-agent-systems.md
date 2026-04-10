---
layout: project
type: research
image: img/code.jpg
title: "Multi-Agent LLM Game for Healthcare Decision Support"
date: October 2025 - Present
published: true
labels:
  - AI
  - Multi-Agent Systems
  - LLMs
  - Optimization
  - Python
  - Flask
  - React
summary: "Designed and built an educational game combining mathematical optimization with multi-agent LLM debate for healthcare operations decision-making under uncertainty."
---
<div class="text-center p-4">
  <img width="600px" src="/img/code.jpg" class="img-thumbnail">
</div>

## Overview

I am a Research Assistant in the College of Engineering and Applied Science at the University of Cincinnati, working under Prof. Tommaso Giovannelli. My work focuses on multi-agent large language model systems applied to decision-making under uncertainty in healthcare operations.

For my capstone project (Spring 2026), I designed and developed an educational game that combines mathematical optimization with AI-driven structured debate. The game teaches students how different assumptions about uncertainty lead to fundamentally different optimal decisions — and that choosing among them requires understanding trade-offs, not just running a solver.

**Role:** Research Assistant – Multi-Agent LLM Systems  
**Institution:** University of Cincinnati, Department of Mechanical and Materials Engineering  
**Advisor:** Prof. Tommaso Giovannelli  
**Dates:** Oct 2025 – Present

---

## The Game

Players take on the role of hospital administrators allocating limited resources (nurses to shifts, or operating room blocks to surgical specialties) under uncertain patient demand. The game proceeds through five steps:

1. **Decide** — Allocate resources using slider controls with real-time cost tracking
2. **Compare to Optimal** — See how your decision compares to three optimization solutions computed under expected, moderate, and worst-case demand assumptions
3. **Observe AI Debate** — Watch three LLM agents (optimistic, pessimistic, mediator) debate the trade-offs across two rounds, culminating in a synthesized final recommendation
4. **Revise** — Adjust your allocation informed by the optimization results and the debate
5. **Evaluate** — Stress-test your initial and revised decisions against multiple demand scenarios

The game implements two healthcare scenarios: Emergency Department Nurse Scheduling (30-bed ED, three 8-hour shifts) and Operating Room Block Allocation (35 weekly blocks across three surgical specialties).

---

## System Architecture

- **Backend:** Python/Flask server with a scipy-based optimization engine using the SLSQP (Sequential Least Squares Programming) algorithm
- **Multi-Agent Debate:** Three LLM agent personas (optimistic, pessimistic, mediator) via the Anthropic Claude API (claude-sonnet-4-20250514), with a structured two-round debate protocol plus mediator synthesis
- **Guardrails:** Allocation clamping, budget constraints, output format validation — inspired by research on autonomous multi-agent supply chain systems
- **Orchestrator:** Controls data flow between agents, enforcing what each agent sees at each debate round
- **Frontend:** React browser interface with a five-step progress flow, slider controls, live debate display, and stress-test evaluation grids

---

## Results

Across three live debate sessions on the nurse scheduling scenario:

- The optimistic agent consistently recommended the cost-minimized solution (23 nurses, $11,500), while the pessimistic agent proposed 30–34 nurses with maximum afternoon staffing
- All three mediator syntheses fell within a narrow range: 27–29 total nurses at $13,500–$14,500
- Agents showed genuine position changes between rounds — the optimistic agent increased its afternoon allocation after seeing the others' proposals, and the pessimistic agent revised downward after triggering the budget guardrail
- The structured debate consistently surfaced the core trade-off: a $4,000 gap (35% cost increase) between cost-minimizing and safety-maximizing solutions

---

## Publication

**Gamage, T.** (2026). "A Multi-Agent LLM Game for Healthcare Decision Support: Combining Mathematical Optimization with AI-Driven Debate for Experiential Learning." Capstone Project, University of Cincinnati.

<p class="mt-4">
  <a href="https://sites.google.com/view/tommasogiovannelli/students?authuser=0"
     target="_blank"
     rel="noopener noreferrer"
     class="btn btn-outline-dark">
    View Research Group
  </a>
</p>
