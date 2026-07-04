# AIMC Tool Landscape

## Purpose

This document provides an overview of the tools available for mainframe system discovery, analysis, operations and knowledge acquisition.

The objective is not only to describe the tools themselves but also to explain:

- what information can be obtained
- when the tool should be used
- which competencies can be developed
- typical limitations
- availability within an enterprise environment

---

## Legend

| Availability | Meaning |
|-------------|---------|
| Common | Usually available in most environments |
| Restricted | Requires special authorization |
| Local | Environment-specific implementation |
| Optional | May not be installed everywhere |

---
| Tool                | Area       | Purpose                         | Typical Use             | Competency            | Availability | Example              |
| ------------------- | ---------- | ------------------------------- | ----------------------- | --------------------- | ------------ | -------------------- |
| ISPF                | Navigation | Mainframe navigation            | Member browsing         | z/OS fundamentals     | Common       | ISPF 3.4             |
| TSO                 | Navigation | Interactive command environment | Dataset operations      | z/OS fundamentals     | Common       | TSO                  |
| SDSF                | Operations | Job and spool monitoring        | Incident analysis       | Operations            | Common       | SDSF                 |
| SPUFI               | DB2        | SQL execution                   | Catalog queries         | DB2 discovery         | Common       | SPUFI                |
| DB2 Browser         | DB2        | DB2 object exploration          | Table analysis          | Data discovery        | Restricted   | DBAJ                 |
| Metadata Repository | Discovery  | Cross-system analysis           | Dependency analysis     | Application mapping   | Optional     | XINFO                |
| Source Repository   | Discovery  | Source management               | Program discovery       | Program analysis      | Local        | YQ01                 |
| Scheduler           | Batch      | Job orchestration               | Batch flow analysis     | Process analysis      | Restricted   | Enterprise Scheduler |
| JCL Repository      | Batch      | JCL inventory                   | Execution flow analysis | Batch competence      | Optional     | XINFO JCL            |
| Programs Repository | Discovery  | Program inventory               | Application mapping     | Program discovery     | Optional     | XINFO Programs       |
| Source Inventory    | Discovery  | Source inventory                | Ownership analysis      | Application discovery | Optional     | XINFO Source         |
| DB2 Catalog         | DB2        | Database metadata               | Data model discovery    | DB2 competence        | Common       | SYSIBM.\*            |
| IMS Repository      | IMS        | IMS metadata                    | IMS discovery           | IMS competence        | Optional     | XINFO IMS            |
| SMF Analysis        | Monitoring | Operational statistics          | Capacity analysis       | Performance analysis  | Restricted   | XINFO SMF            |
| Knowledge Base      | Knowledge  | Documentation and learning      | Mentoring               | Knowledge sharing     | Common       | GitLab               |
