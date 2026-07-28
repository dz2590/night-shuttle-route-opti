# Improving Columbia's Microtransit Shuttle Service with Batch Optimization

## Overview
This project develops a dynamic batching and routing framework for Columbia Transportation's on demand nighttime shuttle service. The devised strategy groups incoming ride requests into rolling time windows, assigns capacity feasible request batches to available shuttles, and optimizes each shuttle's pickup and drop off route using a pickup-and-delivery Traveling Salesperson problem. 

We also perform an exploratory analysis on historical wait times and sensitivity analyses to evaluate how different batching time windows and fleet availability levels can affect overall service performance. Overall, the main objective of this project is to reduce passenger wait times while continuing to serve demand without altering the existing fleet. 

Note that this project was developed for Columbia's IEOR 4418 course. Reproducing the full analysis would require the original restricted data files and a working Gurobi license. 

## Repository Structure
```text
.
├── Batch and Routing.ipynb
├── Preliminary Data Analysis.ipynb
├── IEOR4418_report.pdf
└── README.md
```

### `Preliminary Data Analysis.ipynb`
Contains the exploratory analysis used to define the project scope such as: 
- wait-time calculations
- door-to-door and corner-to-corner comparisons
- completion-rate analysis
- service-period filtering
- descriptive statistics for the month of October
- wait-time distribution visualizations

### `Batching and Routing.ipynb`
Contains the primary simulation and optimization workflow: 
- OpenStreetMap graph construction
- shortest-path distance calculations
- rolling-window batching
- passenger-capacity sub-batching
- vehicle assignment
- Gurobi pickup-and-delivery TSP
- route reconstruction
- dispatch simulation
- sensitivity testing
- simulation performance summaries and plots

### `IEOR4418_report.pdf`
Provides the full mathematical formulation, modeling assumptions, sensitivity results, confidence intervals, limitations, and discussion of results. 

## Technologies and Methods

- Python
- Pandas
- NumPy
- Matplotlib
- NetworkX
- OSMnx
- OpenStreetMap
- Shapely
- Gurobi
- Mixed-Integer Programming
- Pickup-and-Delivery TSP
- Vehicle Routing
- Discrete-Event Simulation
- Sensitivity Analysis

## Environment Requirements
The notebooks use the following third-party Python packages:

```text
pandas
numpy
matplotlib
networkx
osmnx
shapely
tqdm
gurobipy
openpyxl

```
The code also uses Python standard-library modules such as:

```text
datetime
math
xml.etree.ElementTree
dataclasses
typing
```

A valid Gurobi installation and license are required to solve the routing models.

The OpenStreetMap graph-construction step also requires internet access unless the graph is downloaded and saved locally in advance.

## Required Data Files

The original notebooks reference course-provided files such as:

```text
Ride Requests_2025-11-11-part-1.csv
Ride Requests_2025-11-11-part-2.csv
CUL October 2025 Supply Plan.xlsx
shuttle.kml
```

These files may not be included in the public repository because they contain course-provided data specific to the university. Without them, the notebooks cannot reproduce the complete simulation.
