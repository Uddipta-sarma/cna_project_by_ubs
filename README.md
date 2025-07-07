# cna_project_by_ubs
🚗 Project Overview

This project implements a real-time dynamic pricing engine for smart parking management using Pathway. The system computes parking prices based on historical occupancy trends and real-time signals like queue length, traffic, and special day effects. Two models (Model 1 and Model 2) are used to compute prices, which are then visualized and compared to real-time actual pricing.

The goal is to create a fair and scalable pricing strategy that optimizes utilization and responds to real-world demand fluctuations.

🧰 Tech Stack
Component                Technology

Stream Processing        Pathway
Visualization            Bokeh, Panel
Notebook Runtime         Jupyter Notebook
Language                 Python 3.x

⚙️ Architecture & Workflow

Ingest Data: Input CSV or streaming data is read with occupancy, capacity, and timestamp.

Timestamp Processing: The timestamp is parsed into datetime (t) and day string (day).

Windowing: Daily tumbling window applied using pw.temporal.windowby().

Aggregation: Metrics like max occupancy, min occupancy, average queue, etc., are computed.

Model 1:

Simple linear model based on occupancy ratio.

Price = 10 + 5 * (avg_occupancy / cap)

Model 2:

Demand-based price function using multiple signals:

demand = 0.4 * occ_ratio + 0.3 * queue + 0.2 * is_special_day + ...
price = 10 * (1 + 0.5 * normalized_demand)

Visualization: Model 1, Model 2, and Actual Price are plotted via Bokeh & Panel.
![image](https://github.com/user-attachments/assets/ab8c56b6-8fc6-4754-a7ae-09d4ea2738ba)


