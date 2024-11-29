---
title: '**How to Build Your Game Loops in Machinations**'

---

# **How to Build Your Game Loops in Machinations**

# Table of Contents
1. [Date, Time, Location](#datetime--location)
2. [Requirements](#requirements)
3. [Notes](#notes)
4. [Core Loops](#core-loops)
5. [Core Loop Actions w/ Example](#explanation-of-core-loop-actions-example-based)
6. [More Complication]([https://github.com/st8tikratio/Usefulness/new/main/papers/markdown_versions#more-complicated))
7. [Steps & Batch Plays](#steps-and-batch-plays)
8. [Idle Game Loop](#idle-game-loop)
9. [Usage](#usage)
10. [Links](#links)
---
#### **Date/Time & Location**

- 11 Aug 2022 @ 1600 UTC
- Zoom

#### **Requirements**

Must use Google Chrome based browser

#### **Notes**

Core Loops

Overview of popular core gameplay loops

[Session Models](https://machinations.io/community/matthew.16/webinar-examples-of-core-game-4148c35f199511ed8c2902f943517e50/) - Must use Google based browser

---

#### **Core Loops**

- the very heartbeat of your game
- loop of building loops
    - what are the core mechanics?
    - define player actions
    - what are the resources?
    - what do we want to measure?
    - test logic
    - iterate on core logic
    - expand model to include all systems
- may store core loops in a separate container or expand the core loop

---

#### **Explanation of Core Loop Actions (example based)**

Play/pass/fail level loop
Win or lose
- resource pool is used to track player
- resource connection
    - transfer resources
- gate
    - distribution of available outputs
    - can have one or many outputs
    - 2-way split is 50/50

What happens when the player wins or loses?
- advance a level (win)
    - must have a pool with resources for next level
- must put source (triangle)
    - generates resources, nothing more
    - must be conditioned on winning
        - win pool triggers source
            - active
            - passive (example)
    - must use state connection
        - affects the state or resources
        - signifies the trigger

Win pool -> state connection -> source -> resource pool

random gates (diamonds)
- distributes resources randomly

draw two resource connections from the pools to the initial pool
- takes resources from all potential resource pools and brings them to the original resource pool

**Right click on node** select *show chart*

Can expand level via difficulty etc.

Can also insert ads, etc. into the core game loop

---
### **More Complicated**

Training soldiers
- resource pool
- (side-ways) triangle
- resource pool
- random gate (with asterick)
- resource pool

To attack
- adjust state connection to percentage between the *random gate* and the *reosurce pool (output)*
- last resource pool is battle pool
- state connection
- gate (surviving soldiers)
- back to soldier resource pool

Gather resources
- attack resource pool
- send resources back to original resource pool
- source (triangle) with state connection to original resource pool with 
    - state connection (+5 resources)
    - dotted line

Can pull up chart and random indicators on battle pool (soldier statistics, etc.)

---

### **Steps and Batch Plays**

- concept of time called steps (always minimum/maximum of 1 step per action)
- what does the step indicate?
    - fundamental time in machinattions
- batch plays 
    - run the simulation on the server-side
    - using game logic
    - can select the number of batch-plays that can be done
    - can be looked at individually
    - **quicker way of executing and getting faster results**
- steps and speed of model can be adjusted

---

### **Idle Game Loop**

- Pretty basic and good example of what a feedback loop is
- A never ending loop of scenario
- Linear loop

Using source (triangle) [building production]
- state connection
- resource (currency)
- side triangle (change)
- state connection (solid line)
- resource pool [building level]
- create output loop to original resource pool with adjusted resources collected
- connect *building level* to cost fx (function) with dotted line
- connect dotted line from fx to state conenction between *currency* and *upgrade building*

**Go to global connections and choose type of line, can save, can change the size of decimals places, etc.**

**Resources cannot be transfer in decimal, must be integer**
- Machinations rounds to the nearest whole number
- to bypass go to settings and select *round number*

Right click on fx (cost) and view chart to info

Connect multiple buidling loops to each other
- requires connecting the source of building two coming from previous building or vice-versa

To adjust fixed cost to a certain level
- enter a > 10
- can change the formula in the model settings

---

### **Usage**

Duplicate model
- select all
- right-click
- duplicate

Connect models
- connect necessary source(S)

Machinations uses the cheapest options in loops

Can use layers as needed (use to decrease visual clutter)

---

### **Links**

[Machination Website](https://machinations.io)
[Machinations Knowledge Base](https://machinations.io/resources/)
[Machinations Youtube](https://www.youtube.com/c/Machinationsio)


