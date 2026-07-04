# P21 Knowledge Base

## Overview

This repository contains anonymized knowledge, methods, concepts and reusable patterns derived from enterprise mainframe environments.

The repository is intended for:

- knowledge sharing
- mentoring
- onboarding
- architecture discovery
- application understanding
- impact analysis training
- migration preparation
- reusable analysis patterns

No customer-specific, implementation-specific or sensitive information is stored here.

---

## Objectives

The primary objective is not to document a specific system.

The objective is to develop the capability to understand unknown systems by combining:

- technical analysis
- application analysis
- data analysis
- business analysis

The repository supports progressive learning from beginner level to expert level.

---

## Core Principles

### System Understanding

The goal is to understand:

- what exists
- how it works
- how components interact
- what business capability is supported
- what impact a change may have

### Technology-Agnostic Thinking

Tools and technologies are important, but understanding systems is more important than understanding individual products.

The same discovery principles can be applied across:

- DB2
- IMS
- CICS
- Batch processing
- Scheduling environments
- Source code repositories
- Metadata repositories

### Reusable Knowledge

Information should be documented as reusable concepts and patterns rather than system-specific implementations.

---

## Discovery Model

Systems are explored through multiple layers.

```text
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
```

Each layer provides additional context.

---

## Main Discovery Areas

### Applications

Understanding:

- application boundaries
- application groups
- application ownership
- application dependencies

Examples:

- order management
- logistics
- finance
- procurement

### Programs

Understanding:

- program inventory
- program relationships
- source code structure
- execution patterns

### Data

Understanding:

- tables
- views
- indexes
- keys
- relationships

### Processes

Understanding:

- batch flows
- online processes
- scheduling dependencies
- operational procedures

### Business

Understanding:

- business objects
- business terminology
- business capabilities
- business processes

---

## Knowledge Domains

### Tools

Examples:

- ISPF
- SDSF
- SPUFI
- DB2 browsers
- metadata repositories

### DB2

Examples:

- catalog analysis
- object discovery
- dependency analysis
- data model exploration

### Programs

Examples:

- COBOL
- PL/I
- Assembler
- package relationships

### Batch Processing

Examples:

- JCL
- procedures
- scheduler integration
- restart concepts

### Discovery Methodology

Examples:

- application mapping
- dependency analysis
- impact analysis
- system exploration techniques

---

## Learning Path

### Foundation

Focus:

- navigation
- terminology
- basic tools
- object identification

Typical questions:

- What is this object?
- Where is it used?
- Who owns it?

### Practitioner

Focus:

- dependency analysis
- application mapping
- process understanding

Typical questions:

- What depends on this component?
- Which application uses it?
- Which business object does it represent?

### Advanced

Focus:

- architecture analysis
- migration support
- impact assessment

Typical questions:

- What happens if we change it?
- Which systems are affected?
- How does the process work end-to-end?

### Expert

Focus:

- mentoring
- knowledge transfer
- architecture leadership

Typical questions:

- How should knowledge be organized?
- How can others learn this system faster?
- How can the architecture be improved?

---

## Repository Structure

```text
p21/
│
├── README.md
├── glossary.md
│
└── docs/
    ├── discovery-process.md
    ├── tools.md
    ├── db2-discovery.md
    ├── application-discovery.md
    ├── impact-analysis.md
    └── mentoring.md
```

---

## Glossary

A shared vocabulary is maintained in:

```text
glossary.md
```

The glossary contains:

- tools
- technical concepts
- application concepts
- business concepts
- methodology concepts

---

## Intended Audience

This repository is intended for:

- students
- trainees
- junior engineers
- senior engineers
- mentors
- architects
- modernization teams
- migration teams

---

## Disclaimer

This repository contains generalized and anonymized concepts only.

No proprietary business logic, customer-specific implementation details or sensitive operational information should be stored in this repository.
