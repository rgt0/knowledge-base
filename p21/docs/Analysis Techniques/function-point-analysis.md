Analysis Techniques/function-point-analysis.md
# Function Point Analysis

## Purpose

Function Point Analysis (FPA) is a technique used to measure software functionality from a business perspective.

Unlike source code metrics, Function Point Analysis focuses on:

- business functions
- user interactions
- data maintained by the application
- interfaces between applications

The method is technology-independent and can be applied to both legacy and modern systems.

---

## Why Function Point Analysis Matters

Function Point Analysis helps answer questions such as:

- What functionality does the application provide?
- Which business capabilities are supported?
- How large is the application from a business perspective?
- What is the potential impact of a change?
- How can modernization efforts be prioritized?

For system discovery activities, Function Point Analysis provides a structured way to understand how business functionality is implemented.

---

## Core Concepts

### External Inputs (EI)

Business events entering the application.

Examples:

- Create Customer
- Update Order
- Submit Claim

Questions:

- What information enters the system?
- Which programs process the input?
- Which data objects are modified?

---

### External Outputs (EO)

Information produced by the application.

Examples:

- Reports
- Notifications
- Export Files

Questions:

- What information leaves the system?
- Which business users consume it?

---

### External Inquiries (EQ)

Requests that retrieve information without significant processing.

Examples:

- Customer Lookup
- Product Search

Questions:

- Which data is queried?
- Which business process requires the inquiry?

---

### Internal Logical Files (ILF)

Logical groups of data maintained by the application.

Examples:

- Customer
- Order
- Product

Questions:

- Which application owns the data?
- Which programs maintain the data?

---

### External Interface Files (EIF)

Logical data groups used but not maintained by the application.

Examples:

- Reference Data
- Shared Master Data

Questions:

- Which application owns the data?
- How is it consumed?

---

## Relationship to System Discovery

Function Point Analysis can be used as a discovery technique when exploring unknown systems.

The analyst identifies:

- business functions
- logical data entities
- application boundaries
- interface relationships

This creates a business-oriented view of the system.

---

## Relationship to the P21 Discovery Model

Function Point Analysis connects multiple discovery layers.

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

By analyzing functions and data, an analyst can move between technical and business perspectives.

---

## Typical Discovery Questions

### Foundation Level

- What does this program do?
- Which data does it access?
- Which business function does it support?

### Practitioner Level

- Which applications use this data?
- What depends on this component?
- Which functions belong to this application?

### Advanced Level

- What is the impact of a change?
- Which business capabilities are affected?
- Which interfaces must be reviewed?

### Expert Level

- How should functionality be grouped?
- How can knowledge be transferred effectively?
- How can application portfolios be analyzed consistently?

---

## Function Point Analysis as a Learning Tool

Within P21, Function Point Analysis is not primarily used for project estimation.

Its primary value is as a structured approach for:

- application understanding
- dependency discovery
- business capability mapping
- impact analysis
- modernization preparation

The goal is to improve system understanding rather than produce formal size measurements.

---

## Key Takeaway

Function Point Analysis helps bridge the gap between technical implementation and business functionality.

It provides a repeatable method for understanding what a system does, how data is managed, and how business capabilities are delivered.
