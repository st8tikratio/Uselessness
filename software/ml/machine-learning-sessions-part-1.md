---
title: Machine Learning Sessions Part 1.
tags: [lectures, ' ML']

---

---
title: Machine Learning Sessions Part 1.
tags: lectures, ML
---

# Machine Learning Sessions Part 1.

#### Resources are [here](/M78yxeOGQyaqAdlsj7JX3Q)

## Beyond Jupyter Notebooks: MLOps Environment Setup & First Deployment

- 28 Sep 2022
- Youtube
- DeepAI
[Video](https://www.youtube.com/watch?v=4pkzY95Otm4)
[Setup](https://github.com/FourthBrain/software-dev-for-mlops-101)

### Education Source
- Udacity
- Fourth Brain
- Deep AI
- Others

### HW, Software, ETc.
Important to learn at least one instance of each.
- Version Control
    - GIT
        - core aspect --> everything is local
        - GITOps
- The UNIX command line
    - A Shell for UNIX like operating systems
    - Shell
        - CLI
- Package and Environment Management
    - Conda
        - packages
        - package management
        - environment management
- Buidling Web Apps
    - Fast API
    - Flask
    - Django
- Containers
    - Docker
- Visual Studio Code
    - allows for all the above and more

### Installation
- HomeBrew
- WGet
- Miniconda
    - make sure Conda environment is setup
- VSCode
    - once installed
        - start working in VSCode
        - install extensions
            - intellicode
            - jupyter
            - set python interpreter
                - select the conda environment that is being used
                    - print ('Hello MLOps Developer')
- GitHub
    - create a Github portfolio
    - create a new repo to work 
        - select MIT license
- Connect Repo
    - clone repo
    - mkdir local
        - mkdir (code)
    - cd to code directory
        - git clone - https
    - check git remote -v
    - git config
    - git add
    - git commit
    - git checkout
    - git merge
    - git push origin main

### Fast API & Docker Lab
- No batch setup
- [Source](https://github.com/https-deeplearning-ai/machine-learning-engineering-for-production-public/blob/main/course4/week2-ungraded-labs/C4_W2_Lab_1_FastAPI_Docker/README.md) - Part 1
    - Wine Project
- Check out MLFlow
- Missing packages produce error codes
- When running local use /docs if "no detail" error
- Can you plug in new code into pre-existing to create your own program
- To use Docker on M1/2 use Docker Hub
    - same as local host - use /docs

### Questions
- Jupyter Notebook
    - learn to deploy from within
        - toward low code/no code
            - fails at scaling
- Jupyter Hub
- Jupyter Lab
- building quick deoployment tools into platforms can allow quick deployment
    - Azure
    - AWS
    - GCP
- Conda v. Pip v. Poetry
    - incorporates what many data scientist need by default
    - use whatever works for the project
- Best model storage formats
    - depends
    - what kind of metadata is being stored
    - what needs triggers in an ML pipeline
    - **check model registries**
    - everyone is trying to solve a particular problem. Those that solve the problems are typically picked up
    - does a real-time retroactive model setup needed
    - don't overkill solutions to small problems with large tools
- What is best storge solution for model presentation?
    - how many models
    - MLFlow's MLTracking tool
- Why miniconda
    - Full Conda does not work with M-series MBs
- What is wrong with PyCharm?
    - not the industry standard any more

---
---

## Introduction to AI/ML, with KIMO
Kimo
29 Sept 0900
Zoom
[Certificate Request](https://docs.google.com/forms/d/e/1FAIpQLSeRaloSyLLs6QqLGpSgpG8t6A75-szVDWtEZJYzC44vBg_LJQ/viewform)

### Structure of AI

- AI
    - ML
        - DL
            - NLP - natural language processing
            - CV - computer vision
            - Multimodal

### Market - Where is the demand?

![](https://i.imgur.com/bq6pwYq.png)
- First Section - Customer Oriented
- Second Section - Factory Optimization
- Third Section - 

![](https://i.imgur.com/5r4h2RB.png)
![](https://i.imgur.com/ZQR5Mcy.png)

More and more niche providers for AI specific hardware
- Optimized for AI
- Parallel processor for tensors is the optimization plan
![](https://i.imgur.com/spVHYX3.png)
#### Extremely successful AI companies
![](https://i.imgur.com/Z72aY7f.png)
#### How it feels to work in AI
![](https://i.imgur.com/5qm148x.png)
#### Growth Rate
- key point is speed
![](https://i.imgur.com/eFRqrAm.png)
#### Adoption Rate
![](https://i.imgur.com/F0Rrgh8.png)
#### Data Labeling
- quite often performed by human beings
![](https://i.imgur.com/qp3smHp.jpg)

### Technology
- not a single revolution in a single area
![](https://i.imgur.com/NAhErZj.jpg)
![Uploading file..._brbey6356]()
- specialized silicon, TPUs
![](https://i.imgur.com/vwzo20J.png)
- processor sent in oil
#### Edge (local)Computing
- everything stays local on smartphone or other device
![](https://i.imgur.com/sL6O6Dd.jpg)
#### Where is most time spent building a model?
![](https://i.imgur.com/ZgD8kaZ.jpg)
#### Low/no code
- drag and drop
![](https://i.imgur.com/dcEU4f1.png)

### Models & Neural Networks

#### How does a neural network learn?
![](https://i.imgur.com/G39W7IH.jpg)

Set up a model with layers
- each layer contains relative information
- neural netwrok makes connections of the different layers
    - captures values of these connections
    - determines weight of the model
- $f$ goes back into the signal for further evaluation
- make predicitions match available data

Video shown - Visualization of 1989 Neural Network
- Multilayer Perception based on hand written information

#### Training an AI Model (old school)
- [MINIST in Keras.ipynb](https://colab.research.google.com/github/AviatorMoser/keras-mnist-tutorial/blob/master/MNIST%20in%20Keras.ipynb))

#### Training a model today
Complex goal optimization in 3D
- showed video of this - very cool
    - incentivized or reward for winning
- [DALLE 2.0](https://openai.com/dall-e-2/)
- [Midjourney](https://www.midjourney.com/home/)

#### Human AI Interactions in 2022
- Language modeling with text
    - memories, etc.

#### 3D Predictions 2022
- realistic virtual twins
- Metaverse
- virtual factory (BMW) - testing and training before production
    - ![](https://i.imgur.com/4LHRPjj.jpg)
- AGI - artificial general intelligence
    - AI typically focuses on one area
    - ![](https://i.imgur.com/El4qQv9.png)
- Geo-politics
    - Foundation models
    - ![](https://i.imgur.com/Y4MWWLe.png)

### What's Next
![](https://i.imgur.com/Yud5aB5.png)

---
---

## What can Philosophy do for Responsible AI
Date/Time: 12 Oct 2022 @ 1100 UTC (late)
<br>
Host: Dyson School of Design Engineering
<br>
Format: Zoom

**EVENT NEVER HAPPENED in Zoom**

---
---




