# 🚆 NexRail — AI-Based Train Traffic Management System

**NexRail** is an AI-based **Train Traffic Management System (TTMS)** designed to manage railway traffic, detect train conflicts, and generate optimized rescheduling decisions when delays occur.

The primary goal is to **minimize overall delay and prevent unnecessary disruption to trains that are already running on time**.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Solution](#-proposed-solution)
- [Key Features](#-key-features)
- [System Workflow](#-system-workflow)
- [System Architecture](#-system-architecture)
- [Railway Scenario](#-railway-scenario)
- [Optimization](#-optimization-objective)
- [Input Data](#-input-data)
- [Performance Metrics](#-performance-metrics)
- [Technology Stack](#️-technology-stack)
- [Project Structure](#-project-structure)
- [Installation](#️-installation)
- [Usage](#-usage)
- [Future Scope](#-future-scope)
- [Team](#-team)
- [License](#-license)

---

## 🔍 Overview

Railway networks operate with multiple trains sharing limited track infrastructure. A delay in one train can affect several other trains because of track conflicts, limited capacity, train crossings, and minimum headway requirements.

**NexRail** addresses this problem by analyzing train schedules, delays, track availability, train priorities, and operational constraints to determine an optimized traffic-management plan.

### Core Objective

> **When one train gets delayed, NexRail aims to manage the resulting traffic intelligently instead of allowing the delay to propagate unnecessarily across the railway network.**

---

## ❗ Problem Statement

When a train is delayed, railway traffic controllers may need to make decisions regarding:

- Which train should be given priority?
- Which train should be held?
- Which track should be assigned?
- Can another train use an alternative track?
- How can the delayed train recover its schedule?
- How can the delay to other trains be minimized?

Making these decisions becomes increasingly difficult when multiple trains and track sections are involved.

NexRail provides a **data-driven and optimization-based approach** to these traffic-management problems.

---

## 💡 Proposed Solution

NexRail follows the following process:

1. Load train schedules and route information.
2. Monitor train delays and current status.
3. Identify potential track conflicts.
4. Check available tracks and railway constraints.
5. Apply train-priority rules.
6. Generate possible rescheduling decisions.
7. Evaluate the possible solutions.
8. Select the most efficient solution.
9. Generate an optimized train schedule.
10. Compare the original and optimized schedules.

---

## 🚆 Key Features

### 1. Train Monitoring

The system keeps track of:

- Train ID
- Train name
- Current location
- Source and destination
- Scheduled time
- Actual time
- Delay
- Priority
- Assigned track

### 2. Conflict Detection

NexRail identifies situations where multiple trains require the same railway resource during overlapping time periods.

Example:

```text
Train A ───────────────►
              ⚠️ Conflict
Train B ───────────────►
```

The system then evaluates possible solutions.

### 3. Dynamic Rescheduling

When a delay or conflict occurs, NexRail can modify train movement decisions rather than relying only on the original timetable.

### 4. Priority-Based Management

Trains can be assigned different operational priorities.

Example:

| Priority | Train |
|---|---|
| P1 | Vande Bharat |
| P2 | Duronto Express |
| P3 | Jan Shatabdi |
| P4 | Other Trains |

Higher-priority trains can receive preference when conflicts occur, subject to safety and operational constraints.

### 5. Delay Minimization

The system attempts to minimize:

- Total delay
- Average delay
- Maximum delay
- Number of affected trains
- Delay propagation
- Unnecessary train holding
- Track conflicts

### 6. Schedule Comparison

NexRail can compare:

```text
Original Schedule
        ↓
Traffic Simulation
        ↓
Conflict Detection
        ↓
Optimization
        ↓
Rescheduled Schedule
        ↓
Performance Comparison
```

---

## 🔄 System Workflow

```text
┌──────────────────────┐
│   Train Schedule     │
│        Input         │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Train Status & Delay │
│      Analysis        │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Track & Route Check  │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│  Conflict Detection  │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Priority & Constraint│
│      Handling        │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Optimization Engine  │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Optimized Train Plan │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Performance Analysis │
└──────────────────────┘
```

---

## 🛤️ Railway Scenario

NexRail can be configured for a railway corridor such as:

```text
Howrah
   │
   │ 3 Tracks
   ▼
Kharagpur
   │
   │ 2 Tracks
   ▼
Tatanagar
```

### Example Scenario

Suppose:

- A Vande Bharat train is delayed.
- A Duronto Express is running on time.
- A Jan Shatabdi is approaching the same railway section.
- Multiple tracks are available in some sections but limited in others.

NexRail evaluates the situation and determines whether trains should:

- Continue normally
- Be temporarily held
- Change track
- Change crossing sequence
- Be rescheduled

The objective is to give priority where appropriate while **minimizing unnecessary delay to other trains**.

---

## 🧠 Optimization Objective

The optimization engine aims to find a feasible traffic plan that minimizes overall disruption.

A simplified objective can be represented as:

```text
Minimize:

Total Delay
+ Delay Propagation
+ Number
