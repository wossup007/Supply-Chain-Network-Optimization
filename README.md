# Supply Chain Network Optimization

**Outbound Logistics Cost & Capacity Optimization using SQL + Python**

---

## Project Overview

This project optimizes the assignment of customer orders to warehouses in a real outbound logistics network of a global microchip manufacturer.

The historical allocation was highly unbalanced — one plant handled the majority of orders while several other plants remained underutilized. The objective of this project is to reassign orders in a way that reduces total warehouse handling cost while respecting capacity and product-plant compatibility constraints.

---

## Business Problem

- One plant (PLANT03) was processing over 90% of total orders.
- Multiple plants had available capacity but received almost no volume.
- This imbalance increased operational risk and handling costs.

**Goal:** Minimize total warehouse cost while improving load distribution across the network.

---

## Dataset

Real-world logistics dataset containing:

- 9,215 customer orders
- 19 plants with capacity and cost information
- Product–plant compatibility rules
- Plant–port connections and special customer restrictions

---

## Approach

### 1. Data Preparation
- Loaded all source tables into **SQLite**
- Cleaned and transformed the data using **SQL**
- Created analysis-ready tables (orders, capacities, costs, constraints)

### 2. Optimization Logic
- Built a **greedy capacity-aware assignment model** in Python
- For every order, the model selects the lowest-cost plant that:
  - Can produce the required product
  - Still has remaining capacity
- Compared the new assignment against the historical baseline

### 3. Evaluation
- Calculated total cost before and after optimization
- Analyzed changes in plant utilization and order volume

---

## Key Results

| Metric                       | Value             |
|------------------------------|-------------------|
| Historical Total Cost        | $1,563,222        |
| Optimized Total Cost         | $1,554,878        |
| **Cost Savings**             | **$8,444**        |
| Orders Reassigned            | 1,304             |
| Load reduced on PLANT03      | –1,167 orders     |

**Other improvements:**
- Several previously unused plants started receiving orders
- Network utilization became more balanced
- Pressure on the overloaded plant was reduced

---

## Tech Stack

- **SQL (SQLite)** – Data extraction and preparation  
- **Python (Pandas)** – Data processing and optimization  
- **Greedy Algorithm** – Capacity-constrained cost minimization  

---

## Project Structure
Supply-Chain-Network-Optimization/
├── supply_chain_network_optimization.py
├── orders_clean.csv
├── capacities_clean.csv
├── wh_costs_clean.csv
├── product_plant_clean.csv
├── plant_ports_clean.csv
├── vmi_clean.csv
└── README.md

## How to Run

1. Open the Python file in Jupyter Notebook or Google Colab  
2. Ensure the CSV files are in the same folder  
3. Run all cells in order  

---

## Key Insights

- Historical order allocation was heavily concentrated and inefficient.
- A simple capacity-aware assignment rule can still deliver measurable cost savings.
- Better load balancing improves both cost efficiency and operational resilience.

---

## Possible Extensions

- Include freight transportation costs in the objective function  
- Replace the greedy method with a full Linear Programming model (PuLP)  
- Perform scenario analysis (capacity reduction, demand surge, cost increase)

---
