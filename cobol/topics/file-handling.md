---
title: File Handling and Input/Output
category: topic
level: beginner
tags:
  - cobol
  - files
  - io
  - read
  - write
  - display
  - accept
source: mentoring-program-2024
---

# File Handling and Input/Output

## Learning Objectives

After completing this topic, the learner should be able to:

- understand COBOL input/output concepts
- use DISPLAY and ACCEPT statements
- open and close files
- read records from files
- write records to files
- understand end-of-file processing
- understand basic file error handling

---

# Introduction

Input and Output (I/O) is a fundamental part of COBOL programming.

Most enterprise COBOL applications perform one or more of the following operations:

- read data from files
- process records
- write results to files
- display information
- receive user input

---

# DISPLAY Statement

The DISPLAY statement is usually the first executable statement encountered by COBOL beginners.

It writes information to the screen or output device.

Example:

```cobol
DISPLAY "HELLO COBOL".
```

Display a variable:

```cobol
DISPLAY CUSTOMER-NAME.
```

Display multiple values:

```cobol
DISPLAY "CUSTOMER: " CUSTOMER-NAME.
```

Typical uses:

- debugging
- status messages
- reporting
- tracing program execution

---

# ACCEPT Statement

The ACCEPT statement reads input into a data item.

Example:

```cobol
ACCEPT CUSTOMER-NAME.
```

The entered value is stored in the receiving field.

Example:

```cobol
01 CUSTOMER-NAME PIC X(30).

PROCEDURE DIVISION.

    DISPLAY "ENTER CUSTOMER NAME:"
    ACCEPT CUSTOMER-NAME

    DISPLAY CUSTOMER-NAME.
```

---

# File Processing Overview

Typical file processing flow:

```text
OPEN
 ↓
READ
 ↓
PROCESS
 ↓
WRITE
 ↓
CLOSE
```

---

# File Definitions

Files are defined in the DATA DIVISION using an FD entry.

Example:

```cobol
FD CUSTOMER-FILE.

01 CUSTOMER-RECORD.
   05 CUSTOMER-ID     PIC X(10).
   05 CUSTOMER-NAME   PIC X(30).
```

---

# OPEN Statement

Before using a file it must be opened.

Input file:

```cobol
OPEN INPUT CUSTOMER-FILE.
```

Output file:

```cobol
OPEN OUTPUT REPORT-FILE.
```

Input/Output file:

```cobol
OPEN I-O CUSTOMER-FILE.
```

Append processing:

```cobol
OPEN EXTEND REPORT-FILE.
```

---

# READ Statement

The READ statement retrieves the next record from a file.

Example:

```cobol
READ CUSTOMER-FILE
END-READ.
```

With AT END processing:

```cobol
READ CUSTOMER-FILE
    AT END
        MOVE 'Y' TO EOF-SWITCH
END-READ.
```

---

# READ INTO

The INTO clause copies the file record into another storage area.

Example:

```cobol
READ CUSTOMER-FILE
    INTO WS-CUSTOMER-RECORD
END-READ.
```

Advantages:

- preserves file buffer contents
- makes processing easier
- improves readability

---

# End-of-File Processing

Most sequential file programs process records until end-of-file.

Example:

```cobol
READ CUSTOMER-FILE
    AT END
        MOVE 'Y' TO EOF-SWITCH
END-READ.
```

Typical loop:

```cobol
PERFORM UNTIL EOF-SWITCH = 'Y'

    READ CUSTOMER-FILE
        AT END
            MOVE 'Y' TO EOF-SWITCH
    END-READ

END-PERFORM.
```

---

# WRITE Statement

The WRITE statement stores a record in an output file.

Example:

```cobol
WRITE REPORT-RECORD.
```

Writing data from a different structure:

```cobol
WRITE REPORT-RECORD
    FROM WS-REPORT-DATA.
```

Typical use:

- reports
- export files
- output datasets

---

# CLOSE Statement

Always close files after processing.

Example:

```cobol
CLOSE CUSTOMER-FILE.
```

Multiple files:

```cobol
CLOSE CUSTOMER-FILE
      REPORT-FILE.
```

---

# File Status Handling

COBOL does not automatically recover from file errors.

Programs should monitor file status values.

Example:

```cobol
SELECT CUSTOMER-FILE
       ASSIGN TO INPUT01
       FILE STATUS IS WS-FILE-STATUS.
```

Working storage:

```cobol
01 WS-FILE-STATUS PIC XX.
```

Typical situations:

- file not found
- end of file
- invalid key
- record already exists
- access errors

---

# Error Handling Techniques

Common techniques include:

## AT END

```cobol
READ CUSTOMER-FILE
    AT END
        MOVE 'Y' TO EOF-SWITCH
END-READ.
```

## INVALID KEY

```cobol
WRITE CUSTOMER-RECORD
    INVALID KEY
        DISPLAY "WRITE ERROR"
END-WRITE.
```

## FILE STATUS

```cobol
IF WS-FILE-STATUS NOT = "00"
    DISPLAY "FILE ERROR"
END-IF.
```

---

# Typical Batch File Processing

```text
OPEN INPUT FILE-A
OPEN OUTPUT FILE-B

READ FILE-A

WHILE NOT EOF

    PROCESS RECORD

    WRITE FILE-B

    READ FILE-A

END-WHILE

CLOSE FILE-A
CLOSE FILE-B
```

---

# Key Terms

- DISPLAY
- ACCEPT
- OPEN
- READ
- WRITE
- CLOSE
- FILE SECTION
- FD
- FILE STATUS
- AT END
- INVALID KEY

---

# Self-Check Questions

1. What does DISPLAY do?
2. What is the purpose of ACCEPT?
3. Why must a file be opened before reading?
4. What does OPEN INPUT mean?
5. What does WRITE do?
6. What is the purpose of AT END?
7. Why is FILE STATUS important?
8. Why should files always be closed?

---

# Practical Exercise

Create a COBOL program that:

1. Displays a prompt using DISPLAY.
2. Reads a customer name using ACCEPT.
3. Displays the entered value.
4. Defines a sequential file.
5. Opens the file in INPUT mode.
6. Reads records until end-of-file.
7. Closes the file.

Explain the purpose of:

- DISPLAY
- ACCEPT
- OPEN
- READ
- CLOSE
