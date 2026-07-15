# P21 Documentation

## Purpose

This directory contains the core knowledge material used for system discovery, application understanding, impact analysis, mentoring and knowledge transfer.

The documents are organized around the progressive understanding of enterprise systems, from technical components to business capabilities.

---
##Structure
p21/
│
├── README.md
├── glossary.md
│
└── docs/
    ├── README.md
    ├── discovery-process.md
    ├── tools.md
    ├── db2-discovery.md
    ├── application-discovery.md
    ├── impact-analysis.md
    ├── mentoring.md
    └── function-point-analysis.md
## Reading Path

### Foundation

Start here when learning a new environment.

- discovery-process.md
- tools.md
- glossary.md

Typical questions:

- What is this object?
- Where can I find information about it?
- Which tools should I use?

---

### Application Discovery

Focus on understanding applications and their boundaries.

- application-discovery.md
- db2-discovery.md

Typical questions:

- What application does this component belong to?
- Which data does it own?
- Which interfaces exist?

---

### Analysis

Focus on understanding dependencies and change impact.

- impact-analysis.md
- function-point-analysis.md

Typical questions:

- What depends on this object?
- What happens if it changes?
- Which business functions are affected?

---

### Mentoring

Focus on knowledge transfer and capability development.

- mentoring.md

Typical questions:

- How should knowledge be organized?
- How can system understanding be accelerated?
- How can junior engineers become productive faster?

---

## Discovery Perspective

Documents in this repository support analysis across multiple layers:

Business Process
↑
Business Capability
↑
Application
↑
Program / Package
↑
Database Objects
↑
Physical Data

Understanding improves as more layers are connected.

---

## Recommended Learning Sequence

1. Discovery Process
2. Tools
3. Application Discovery
4. DB2 Discovery
5. Impact Analysis
6. Function Point Analysis
7. Mentoring

---

## Guiding Principle

The objective is not to memorize systems.

The objective is to learn how to understand unknown systems quickly, consistently and independently.
