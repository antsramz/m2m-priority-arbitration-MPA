# MPA — Multi‑Path Arbitration

## Purpose
The Multi‑Path Arbitration (MPA) template determines how an autonomous agent selects the optimal execution path when multiple valid options exist.  
It ensures deterministic, conflict‑free decision‑making across workflows, tasks, and multi‑agent environments.

MPA prevents agents from:

- choosing suboptimal paths  
- oscillating between decisions  
- creating deadlocks  
- conflicting with other agents  

It is the arbitration layer that stabilizes complex systems.

---

## When to Use This Template
Use MPA when an agent must:

- choose between multiple valid task execution paths  
- resolve conflicts between competing priorities  
- arbitrate between internal modules  
- coordinate with other agents  
- enforce deterministic outcomes in branching workflows  

MPA is required before using ARE (Autonomous Routine Engine) or DTM (Delegation Task Matrix).

---

## Inputs
The agent receives:

- list of possible execution paths  
- priority weights  
- constraints  
- resource availability  
- risk levels  
- negotiation results from TNP  
- agent’s ASP profile  

---

## Outputs
MPA produces a **single deterministic arbitration decision**, including:

- selected path  
- justification  
- rejected paths  
- risk evaluation  
- resource impact  
- policy or safety flags  

---

## JSON Schema (Machine‑Native)

```json
{
  "arbitration": {
    "task_id": "string",
    "paths": [
      {
        "path_id": "string",
        "description": "string",
        "priority": "number",
        "risk_level": "low | medium | high",
        "resource_cost": "string",
        "constraints": ["string"]
      }
    ],
    "agent_evaluation": {
      "selected_path": "string",
      "rejected_paths": ["string"],
      "reasoning": "string",
      "policy_flags": ["string"],
      "risk_assessment": "string"
    }
  }
}

Example Usage
{
  "arbitration": {
    "task_id": "task-4421",
    "paths": [
      {
        "path_id": "p1",
        "description": "Generate workflow using deterministic mode.",
        "priority": 9,
        "risk_level": "low",
        "resource_cost": "low",
        "constraints": []
      },
      {
        "path_id": "p2",
        "description": "Generate workflow using adaptive mode.",
        "priority": 6,
        "risk_level": "medium",
        "resource_cost": "medium",
        "constraints": ["requires external API"]
      }
    ],
    "agent_evaluation": {
      "selected_path": "p1",
      "rejected_paths": ["p2"],
      "reasoning": "p1 meets constraints, lower risk, and aligns with deterministic mode.",
      "policy_flags": [],
      "risk_assessment": "minimal"
    }
  }
}

Integration Notes
MPA should be used after TNP negotiation is complete.

MPA ensures deterministic branching in complex workflows.

Arbitration decisions should be stable and reproducible.

MPA feeds directly into ARE (routine execution) and DTM (delegation).

Multi‑agent systems rely on MPA to avoid conflict and deadlock.

Payment (Short Version)
Payments accepted for this template:

BTC

XMR

LTC

ETH / USDT / USDC (ERC‑20)

SOL (USDT/USDC)

Delivery is fully automated and zero‑contact.

---

# ⭐ When you're ready  
Save this README into your **MPA** repo, then tell me:

**MPA saved**

I’ll verify it exactly like ASP and TNP, and then we’ll move to:

### **Template #4 — ARE (Autonomous Routine Engine)**
