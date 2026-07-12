---
title: Data Types and Variables
category: topic
level: beginner
tags:
  - cobol
  - data
  - variables
  - picture-clause
  - working-storage
source: mentoring-program-2024
---

# Data Types and Variables

## Learning Objectives

After completing this topic, the learner should be able to:

- understand COBOL data definitions
- define variables using PICTURE clauses
- distinguish between numeric and alphanumeric data
- initialize data fields
- use variables in COBOL programs
- understand the role of WORKING-STORAGE

---

# Introduction

Data is the central element of every COBOL application.

Most COBOL programs perform one or more of the following activities:

- read data
- validate data
- transform data
- store data
- report data

To work with data, developers must understand COBOL data definitions and variable declarations.

---

# COBOL Data Definitions

Data definitions are typically stored in the:

```cobol
DATA DIVISION.
```

Within the DATA DIVISION, variables are usually declared in:

```cobol
WORKING-STORAGE SECTION.
```

Example:

```cobol
DATA DIVISION.

WORKING-STORAGE SECTION.

01 WS-NAME         PIC X(30).
01 WS-AGE          PIC 9(3).
```

---

# Variable Declaration

Variables represent information used during program execution.

Typical examples:

- customer names
- account numbers
- balances
- counters
- status flags

A variable is defined using a data description entry.

Example:

```cobol
01 CUSTOMER-NAME PIC X(30).
```

---

# Alphanumeric Data

Alphanumeric data is defined using the character:

```cobol
X
```

Example:

```cobol
01 CUSTOMER-NAME PIC X(30).
```

This field can contain:

```text
JOHN DOE
```

or

```text
CUSTOMER-0001
```

Typical uses:

- names
- addresses
- identifiers
- free text

---

# Numeric Data

Numeric data is defined using the character:

```cobol
9
```

Example:

```cobol
01 CUSTOMER-AGE PIC 9(3).
```

Possible values:

```text
000
999
```

Typical uses:

- counters
- quantities
- balances
- calculations

---

# Signed Numeric Data

To allow positive and negative values:

```cobol
01 ACCOUNT-BALANCE PIC S9(7).
```

The character:

```cobol
S
```

indicates a signed field.

Examples:

```text
+1200
-1200
```

---

# Decimal Values

An implied decimal point is represented by:

```cobol
V
```

Example:

```cobol
01 PRICE PIC 9(5)V99.
```

Possible value:

```text
12345.67
```

Stored internally without a physical decimal point.

---

# Working-Storage Section

The WORKING-STORAGE SECTION contains variables used during program execution.

Example:

```cobol
WORKING-STORAGE SECTION.

01 WS-CUSTOMER-ID      PIC X(10).
01 WS-CUSTOMER-NAME    PIC X(30).
01 WS-BALANCE          PIC S9(7)V99.
01 WS-COUNTER          PIC 9(5).
```

These values remain available while the program is running.

---

# Variable Initialization

Variables can be initialized using the VALUE clause.

Example:

```cobol
01 WS-STATUS PIC X VALUE 'A'.

01 WS-COUNTER PIC 9(5)
   VALUE ZERO.
```

Examples:

```text
'A'
0
100
```

---

# Moving Data

The MOVE statement copies values between variables.

Example:

```cobol
MOVE 'JOHN DOE'
  TO WS-CUSTOMER-NAME.
```

Example:

```cobol
MOVE WS-BALANCE
  TO WS-PREVIOUS-BALANCE.
```

---

# Reading and Updating Data

Data is often:

- read
- modified
- written back

Example:

```cobol
ADD 1 TO WS-COUNTER.
```

Example:

```cobol
MOVE 'ACTIVE'
  TO WS-STATUS.
```

---

# Typical Data Types

| Type | Example | Usage |
|--------|--------|--------|
| PIC X | PIC X(30) | Text |
| PIC 9 | PIC 9(5) | Integer Numbers |
| PIC S9 | PIC S9(7) | Signed Numbers |
| PIC 9V99 | PIC 9(5)V99 | Decimal Numbers |

---

# Best Practices

- Use meaningful variable names.
- Define field lengths carefully.
- Initialize important variables.
- Separate business data from technical counters.
- Use signed fields when negative values are possible.

---

# Key Terms

- Variable
- Data Field
- Data Definition
- DATA DIVISION
- WORKING-STORAGE SECTION
- PICTURE Clause
- PIC X
- PIC 9
- PIC S9
- VALUE Clause
- MOVE Statement

---

# Self-Check Questions

1. What is the purpose of the DATA DIVISION?
2. What is the difference between PIC X and PIC 9?
3. Why is the WORKING-STORAGE SECTION important?
4. What does the VALUE clause do?
5. What does the symbol S represent?
6. What does the symbol V represent?
7. How does the MOVE statement work?

---

# Practical Exercise

Create a WORKING-STORAGE SECTION containing:

- a customer name
- a customer identifier
- an account balance
- a transaction counter

Initialize all variables using VALUE clauses.

Then:

1. Move a new customer name into the name field.
2. Increase the transaction counter.
3. Display all values.
