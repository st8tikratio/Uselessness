---
title: Machinations Study Group

---

# Machinations Study Group


**Hosts:** @Rohan Sundar  @Mark D @Teal  @stellaachenbach]
**Time & Day:** Thursday, 1600 UTC
[Machinations Youtube](https://www.youtube.com/c/Machinationsio)
[Notion](https://www.notion.so/te-academy/Machinations-Study-Group-49068407abbd4bcfad949cddab73a223)
[Machinations](https://machinations.io/)
[Group Project Documentation](https://docs.google.com/document/d/1Myrj_orxwCKI-IfpI3RfcDTY0UPyghUWjRAzFag6BoI/edit)
    - Rohan

## Recodings
[Session°01](https://drive.google.com/drive/folders/1AnFGi9Vmjd3T_7cxZUcs8cNMpHMdm_a3?usp=sharing)
[Session°02](https://drive.google.com/drive/folders/1bRDp-vksn6QIqMpdH62_uJyr0grc12hO?usp=sharing)
[Session°03](https://drive.google.com/drive/folders/1ZmX1b1XLm9RPH2PmRKdVnOLHyELjepUt?usp=sharing)
[Session°04](https://drive.google.com/drive/folders/1SSr0FIuGidtE8Ll3Q2CcsBVM36k-DA60?usp=sharing)


## Session 1 - Absent

[Recording](https://drive.google.com/drive/folders/1AnFGi9Vmjd3T_7cxZUcs8cNMpHMdm_a3?usp=sharing)

## Session 2 - 25 Aug 2022 - Simple Modeling

**Machinations is a **Turing Complete** system.**

**Formulas and other info** - [HERE](https://my.machinations.io/d/Copy-of-Registers-102-webinar/00e7ca69275999f4d4e907c4021d84ec8)

[Webinar: Simplified Example Token Side AMM](https://machinations.io/community/matthew.16/webinar-simplified-example-token-side-amm-ccff2f0fe9a111ec8c2902f943517e50/)

[Easy Level Progression](https://machinations.io/docs/tutorials-examples/easy-level-progression/)
    - Use Brave or other Chrome based browser

[Webinar: Building a game from start to finish using Machinations (Part 1: Game Mechanics)](https://www.youtube.com/watch?v=JMTo_FberLw&t=1342s&ab_channel=Machinations)

## Session 3 - 01 Sep 2022 - Nodes

**Machinations only works with integers and no decimals**
- cannot **transfer** fractions or negative numbers
- would require the use of smaller numbers
    - i.e. .0001 = 10000 and everything else follows suit
        - i.e. 10 = 100000000

**Node Elements of Machinations**
- no affiliation with blockchain nodes

**Node bar**
- left hand side of Machinations project window

**Nodes (in order)**
- *Source* - upward triangle with asterick
    - generates a resource
    - infinite resources
- *Pool* - circle
    - will never be negative
- *Drain* - downward triangle
    - destroys resources
    - can be considered any means to use/spend resources
    - can use a **Pool** instead to show spent/burned resources
- *Gate* - diamond
    - controls distribution
        - prioritized by node ID
            - lowest first
    - deterministic
        - follows same rules always
    - random
        - shows dice in the middle
        - a higher percentage signifies a higher chance of receiving resources
    - can also drain resources with precentages that total less than 100% 
    - also called **a middle step node**
        - can speed up depending on the setup
- *Converter* - side triangle with vertical line
    - converts x into (n)y
    - singleton
        - makes on conversion per step
        - can be used with multiple
    - multiple
        - converts as many as possible
        - can be used with singleton
    - if inputs, i.e. resource pools do not have enough resources the converter will stop
- *Trader* - two opposing triangles sharing single vertical line
    - cannot function without color coding
    - trades resources based on logic and color
    - can be considered a **double converter**
    - great where people have low resources
- *Delay* - circle with hour glass
    - holds resources until a certain number of steps
    - can also be used in **Que**
        - subsequent resources are released after a certain number of steps
- *End Condition* - box with black box
    - consition to stop the entire simulation
    - could be "game over"
- *Register* - $fx$
    - [Registers - Documentation](https://machinations.io/docs/registers/)
    - watch the Youtube video and/or webinar -> 102 
    - used for all logic/math in the model
- *Connections*
    - **Resource** - solid line
        - sends resources only
        - has interval and instant transfer modes
            - instant is faster connection
            - interval can send resources every step or **less often**
        - **d10** equivalent to rolling a ten-sided dice
        - **all** works a resource connection label
    - **State** - dotted line
        - never used to transfer resources
        - interacts with the state of the other nodes
            - +1 indicates the same is resource is placed on the other node
            - +2 doubles the resources on the other node
        - a drain attached to the left node will remove resources from the right node
        - example
            - source -> pool -> state connection -> pool -> drain
                - allows developer to track rewards and spending
        - can have a filter assigned as well
        - can also influence the resource connection

**Node states**
- passive
    - requires external trigger
- interactive
    - double edged node
    - only performs action when clicked on
- automatic
    - performs action at every step
- enabling
    - performs action the first time it is activated during execution and then stops

**If your model is only concerned with wins then only show wins in the model and do not show loses**

**Color Coding**
- resources can be 
    - black 
    - red 
    - green 
    - blue 
    - orange

## Session 04 - Absent

[Recoding](https://drive.google.com/drive/folders/1SSr0FIuGidtE8Ll3Q2CcsBVM36k-DA60?usp=sharing)

## Session 05

## Session 06
- Went over modeling of basics and more advanced models.
- Discussed formulas [[registers]](https://machinations.io/docs/registers/) available on Machinations.
- [Infinite Runner Game Loop - Tutorial](https://machinations.io/docs/tutorials-examples/infinite-runner-game-loop/)

## Session 07 - Absent

## Session 08
>NOT RECORDED by host
- Teaching is mostly over now
- Jarvis Labs demoed Axie Infinity model briefly
- Machinations introduced [**Custom Variables**](https://machinations.io/docs/what-are-custom-variables/)












