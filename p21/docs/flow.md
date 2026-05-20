# p21 Batch Process – Flow Description

## Overview

The batch process follows a standard cursor-based processing pattern with optional execution logic and restart capability.

The flow remains consistent across test and normal execution modes.

---

## High-Level Flow

The overall execution consists of three main phases:

1. Initialization  
2. Main Processing Loop  
3. Finalization  

---

## 1. Initialization

During the initialization phase:

- Runtime parameters are loaded  
- Restart settings are evaluated  
- Processing context is prepared  

If restart mode is active, a control point is initialized.

---

## 2. Main Processing

### Step 1 – Open Data Source

- A cursor is opened to access the dataset  

---

### Step 2 – Fetch First Record

- The first record is retrieved  
- End-of-data condition is evaluated  

---

### Step 3 – Processing Loop

The system enters a loop that continues until:

- No more data is available, or  
- Processing is stopped  

---

### Loop Steps

#### 3.1 Restart Filter

- Records are compared with the restart key  