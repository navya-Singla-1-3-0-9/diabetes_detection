# Diabetes Diagnosis Using Modified Crow Search Algorithm (CSA) and Harmonic Search (HS)

This repository contains the implementation of a **Diabetes Diagnosis System** based on a hybrid approach combining the **Crow Search Algorithm (CSA)** and **Harmonic Search (HS)**. The goal is to accurately predict diabetes in patients by optimizing feature selection using these metaheuristic algorithms.

## Table of Contents

- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Model Architecture](#model-architecture)
- [Installation](#installation)
- [Usage](#usage)

## Introduction

Diabetes is a chronic disease that occurs either when the pancreas does not produce enough insulin or when the body cannot effectively use the insulin it produces. This project aims to develop a highly accurate prediction system for diagnosing diabetes by modeling it as a **multi-objective optimization problem**.

## Project Overview

This system is designed to predict diabetes using the **PIMA Indian Diabetes Dataset**. The main innovation in this project is the **hybrid approach** that combines:

- **Crow Search Algorithm (CSA):** A population-based optimization algorithm that mimics the intelligent behavior of crows.
- **Harmonic Search (HS):** A metaheuristic algorithm inspired by musical harmony processes, used for enhancing the optimization process.

By merging these algorithms, we enhance the feature selection process and optimize the classification task to predict diabetes more accurately.

## Architecture
This  bald eagle search (BES) algorithm, which is a novel, nature-inspired meta-heuristic optimization algorithm that mimics the hunting strategy or intelligent social behavior of bald eagles as they search for fish.
We have used the space selection phase of the bald eagle algorithm, after the crow search optimization step of following a random crow to its hiding place. This step optimizes the local search capabilities of the algorithm by searching around the best area found so far. This step is followed by the modified search phase of the bald eagle, this step is modified by the sine-cosine algorithm (ref. https://www.sciencedirect.com/science/article/abs/pii/S0950705115005043 ), so this enables the algorithm to adaptively balance the exploration and exploitation phases of the algorithm. The stealing-phase of the crow search algorithm is optimized by a weight matrix, and chaotic maps are used for the flight length variable.

**Step 1**: A swarm of crows in the n dimensional search space is initialized, with the algorithm assigning a random vector xi = (x1,x2…..xn) for ith crow. Furthermore, each crow is characterized by its memory (i.e., initially, a crow’s memory is filled with its initial position, mi = (m1,m2,…mn) , with all crows having no experience regarding food sources). Chaotic variable fl and fixed variable AP are initialized.

**Step 2**: Each crow is evaluated according to the quality of its position, which is related to the desired objective function. Best position (Xbest) is calculated as the position giving maximum fitness (memory).

**Step 3**: Crows create new locations inside the search space as follows: crow i selects one of the crows from the swarm randomly, i.g., crow j , and follows it to determine the location of food hidden by this crow, with the new location of crow i being generated as follows:

<img width="468" alt="image" src="https://github.com/user-attachments/assets/2ba9db72-b589-4f88-8a04-4d9b8a0829ee">

Here, aj is a chaotic number
This step assists in discovery of new search spaces(exploration)

**Step 4**: Position & Memories of crows are updated based on selection step of bald eagle Search Optimization for each iteration as follows:

<img width="450" alt="image" src="https://github.com/user-attachments/assets/2ca64d09-ce0b-43b4-a51e-55aa4866b2fc">

where α is the parameter for controlling the changes in position that takes a value between 1.5 and 2 and r is a random number that takes a value between 0 and 1. This step ensures selection of optimal search space till now. In this step, crows search around the best area.

**Step 5**: Positions of crows are updated based on sine-cosine updated search-step of bald eagle optimization as follows:

<img width="450" alt="image" src="https://github.com/user-attachments/assets/d7635902-3c34-42ec-a5dc-bf4b86576f3f">

<img width="450" alt="image" src="https://github.com/user-attachments/assets/40a51ebe-fec1-4784-8a6e-1cd84f174120">

Where r1 and r2 are random variables.

**Step 6**: Update flight length through Sinusoidal Chaotic map.

<img width="234" alt="image" src="https://github.com/user-attachments/assets/eead780d-9690-47a7-ab12-f56254a7c223">

**Step 7**: Update memory matrix as best memory achieved till now for every point.

**Step 8**: The algorithm is ended if the maximum number of iterations is met and the best location is determined from memory based on the objective function, which is then recorded as the optimal solution of the candidate problem.

## Installation

### Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Python 3.8 or above
- Required Python libraries (see `requirements.txt`)

### Clone the Repository

```bash
git clone https://github.com/yourusername/diabetes-detection.git
cd diabetes-detection


