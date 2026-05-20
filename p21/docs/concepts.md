# Core Concepts – p21 Batch Process

This document defines the key concepts used in the batch processing model.

---

## 1. Restart

### Definition

Restart is a mechanism that allows a batch process to continue from a previously defined point instead of starting from the beginning.

---

### Purpose

- Avoid reprocessing already handled records  
- Enable recovery after interruption  
- Improve processing efficiency  

---

### Mechanism

A control key (restart key) is stored and used as a reference point.

During processing:
If record key > restart key  → process
If record key ≤ restart key → skip

---

### Key Properties

- Deterministic behavior  
- Based on ordered data (e.g. timestamp or technical key)  
- Requires consistent key comparison  

---

### Typical Use Case

- Batch job fails after partial completion  
- Restart is executed with the last successful key  
- Processing continues without duplication  

---

## 2. Test Mode

### Definition

Test mode is an execution mode in which the full processing logic is executed, but no persistent data changes are applied.

---

### Purpose

- Validate processing logic safely  
- Enable repeated execution without side effects  
- Support debugging and analysis  

---

### Behavior

- All processing steps are executed  
- Decision logic is evaluated  
- Data modification actions are suppressed or neutralized  
- Database state remains unchanged  

---

### Implementation Patterns

Two common approaches:

#### 1. Execution Skip

- Data modification actions are not called  
- Only logging or simulation occurs  

#### 2. Execute + Rollback

- All actions are executed  
- A final rollback restores the original data state  

---

### Key Properties

- Safe to run multiple times  
- No impact on production data  
- Same processing path as normal mode  

---

## 3. Commit

### Definition

Commit is the operation that makes all changes within a transaction permanently visible in the database.

---

### Purpose

- Ensure data persistence  
- Define transaction boundaries  
- Maintain data consistency  

---

### Behavior

- Changes are accumulated during processing  
- Commit writes these changes permanently  
- After commit, changes cannot be rolled back  

---

### Commit Strategy

Two common strategies:

#### 1. End-of-Process Commit

- Commit is executed once after the full process  
- Simpler but higher risk in case of failure  

#### 2. Periodic Commit

- Commit is executed after a defined number of records  
- Improves stability and recovery capability  

---

### Key Properties

- Defines transaction scope  
- Impacts performance and recoverability  
- Works together with restart logic  

---

## Summary

These concepts form the foundation of the batch processing model:

- Restart → controls continuation of processing  
- Test Mode → ensures safe and repeatable execution  
- Commit → ensures persistence and consistency  

Together, they enable reliable, controllable, and testable batch processing.
