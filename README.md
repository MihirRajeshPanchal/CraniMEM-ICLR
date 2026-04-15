# CraniMem: Cranial-Inspired Gated and Bounded Memory for Agentic Systems

<img width="11310" height="5110" alt="Cranimem" src="https://github.com/user-attachments/assets/258eb812-063b-4c14-b557-6078bb08fa9f" />



## Overview

Modern LLM agents require persistent memory beyond a single context window. Conventional approaches often treat memory as an external database with heuristic read and write rules, which can lead to unstable retention, noise accumulation, weak consolidation, and poor long-term consistency.

CraniMem models memory as a gated, multi-stage cognitive process inspired by biological systems. Incoming information is filtered for relevance, stored in a bounded episodic buffer for short-term continuity, selectively consolidated into a structured knowledge graph for durable recall, and retrieved through a dual-path mechanism that combines short-term and long-term context.

---

## Key Features

- Goal-conditioned input gating to filter irrelevant information  
- Utility tagging based on importance, surprise, and emotional salience  
- Bounded episodic buffer for recent interaction traces  
- Structured long-term semantic memory using a knowledge graph  
- Replay-based consolidation with pruning of low-utility items  
- Dual-path retrieval from episodic and semantic stores  
- Robustness to distractor noise in long interactions  

---

## Architecture (High Level)

CraniMem implements a gated, bounded, multi-stage memory pipeline:

1. Collection Phase
   Incoming inputs are filtered by relevance and assigned utility scores.

2. Short-Term Storage
   Accepted items are stored in a bounded episodic buffer.

3. Consolidation Phase
   High-utility traces are replayed into long-term memory while low-utility items are discarded.

4. Long-Term Storage
   Durable information is stored in a structured knowledge graph.

5. Retrieval Phase
   Context is assembled from both episodic and semantic memory to condition the LLM.

---

## Core Components

**Episodic Buffer**
Stores recent interaction traces with full fidelity for short-term continuity. The buffer is bounded to prevent unbounded growth.

**Knowledge Graph Store**
Maintains durable semantic information as structured entities and relationships, enabling multi-hop retrieval.

**Gating Module**
Filters inputs based on relevance to the current goal to prevent noise from entering memory.

**Consolidation Engine**
Periodically transfers high-utility experiences from the episodic buffer to long-term storage and prunes low-value items.

**Dual-Path Retrieval**
Combines short-range context from the episodic buffer with long-range knowledge from the graph.

---

## Use Cases

CraniMem is suitable for applications requiring persistent, coherent memory:

* Long-running conversational agents
* Research and analysis assistants
* Planning and workflow agents
* Multi-session copilots
* Personalized systems
* Multi-agent coordination

---

## Limitations

* Higher latency than simple retrieval systems
* Additional infrastructure requirements (e.g., graph database)
* Performance depends on gating and utility scoring quality
* Increased computational cost during consolidation

##  Citation

If you find this work useful in your research or projects, please consider citing:

```bibtex
@article{mody2026cranimem,
  title={CraniMem: Cranial Inspired Gated and Bounded Memory for Agentic Systems},
  author={Mody, Pearl and Panchal, Mihir and Kar, Rishit and Bhowmick, Kiran and Karani, Ruhina},
  journal={arXiv preprint arXiv:2603.15642},
  year={2026}
}
```
---




