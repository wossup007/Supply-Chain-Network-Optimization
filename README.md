Here’s a **super professional README** you can copy-paste directly into your GitHub repository.

---

```markdown
# Supply Chain Network Optimization

**Outbound Logistics Cost & Capacity Optimization using SQL and Python**

---

### Project Overview

This project optimizes the assignment of customer orders to warehouses (plants) in a real-world outbound logistics network. The goal is to minimize total warehouse handling costs while respecting plant capacity constraints and product-plant compatibility rules.

The historical assignment was heavily unbalanced — one plant was severely overloaded while several others remained underutilized. This project redesigns the assignment using a capacity-aware greedy optimization approach.

---

### Business Problem

- One plant (PLANT03) was handling over 92% of total orders despite limited capacity.
- Multiple plants had available capacity but received almost no orders.
- This imbalance increased operational risk and warehouse handling costs.

**Objective:**  
Reassign orders to feasible plants in order to reduce total cost and improve load balancing across the network.

---

### Dataset

Real-world outbound logistics dataset from a global microchip manufacturer containing:

- 9,215 customer orders
- 19 plants/warehouses with capacity and cost data
- Product-plant compatibility constraints
- Plant-port connections and special customer restrictions

---

### Methodology

1. **Data Preparation (SQL + Python)**
   - Loaded all source tables into SQLite
   - Cleaned and joined order, capacity, cost, and constraint tables
   - Created analysis-ready datasets

2. **Optimization Model**
   - Developed a **greedy capacity-aware assignment algorithm**
   - For each order, selected the lowest-cost plant that:
     - Can produce the required product
     - Still has remaining capacity
   - Compared the optimized assignment against the historical baseline

3. **Performance Evaluation**
   - Calculated total warehouse cost before and after optimization
   - Analyzed changes in plant utilization and order distribution

---

### Key Results

| Metric                        | Value              |
|------------------------------|--------------------|
| Historical Total Cost        | $1,563,222        |
| Optimized Total Cost         | $1,554,878        |
| **Cost Savings**             | **$8,444**        |
| Orders Reassigned            | 1,304             |
| Major Load Reduction         | PLANT03: -1,167 orders |

**Additional Improvements:**
- Several previously unused plants started receiving orders
- Network utilization became significantly more balanced
- Overloaded plant pressure was reduced

---

### Tech Stack

- **SQL (SQLite)** – Data extraction, cleaning, and preparation
- **Python (Pandas)** – Data manipulation and optimization logic
- **Greedy Algorithm** – Capacity-constrained cost minimization
- **Jupyter / Google Colab** – Analysis environment

---

### Project Structure

```
Supply-Chain-Network-Optimization/
│
├── supply_chain_network_optimization.py
├── orders_clean.csv
├── capacities_clean.csv
├── wh_costs_clean.csv
├── product_plant_clean.csv
├── plant_ports_clean.csv
├── vmi_clean.csv
└── README.md
```

---

### How to Run

1. Open the Python file in Jupyter Notebook or Google Colab
2. Make sure the CSV files are in the same directory
3. Run all cells sequentially

---

### Key Insights

- Historical order allocation was highly concentrated and inefficient.
- Even a relatively simple capacity-aware assignment rule can deliver measurable cost savings.
- Load balancing across the network improves operational resilience.

---

### Future Improvements

- Incorporate freight transportation costs into the objective function
- Replace the greedy heuristic with a full Linear Programming (PuLP) model
- Add scenario analysis (capacity shocks, demand surges, cost increases)

