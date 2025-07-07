# Summer-Analytics-Program
# 🚗 Real-Time Parking Price Prediction System using Pathway

A real-time dynamic pricing system that monitors parking lot data and computes optimal daily prices using advanced analytics and contextual information like traffic, vehicle type, and special days.

---

## 📌 Overview

In urban areas, pricing parking smartly can help manage demand and reduce congestion. This project demonstrates a **real-time dynamic pricing engine** for parking systems using **Pathway**, a powerful stream processing engine.

It features:
- Stream-based data aggregation (occupancy, queue, traffic)
- Three pricing models for flexibility and benchmarking
- Live plotting of model-based prices
- Easy extensibility for deployment or integration

---

## 🛠️ Tech Stack

| Layer              | Technology Used                |
|-------------------|--------------------------------|
| Data Streaming     | Pathway (Python)               |
| Time Windows       | Pathway's Tumbling Windows     |
| Visualization      | Bokeh, Panel                   |
| Development Env    | Jupyter Notebook               |
| Optional Output    | CSV / Kafka / REST endpoint    |

---

## 🧠 Architecture Diagram

![mermaid-ai-diagram-2025-07-07-134514](https://github.com/user-attachments/assets/c9485932-49b2-4e59-beb2-7c677ff0394b)

⚙️ Workflow Explained
Data Ingestion
Simulated or live parking data is ingested into a Pathway stream (data_with_time). It includes:

SystemCodeNumber, Occupancy, Capacity, QueueLength, TrafficConditionNearby, VehicleType, IsSpecialDay, and timestamp.

Daily Tumbling Window
Using pw.temporal.tumbling(datetime.timedelta(days=1)), we aggregate data by lot and day.

Three Pricing Models

Model 1: Basic occupancy ratio model.

Model 2: Advanced pricing using traffic, vehicle, queue, special events.

Model 3: Captures demand volatility via max-min occupancy spread.

Computed Columns
Intermediate values like average occupancy and queue length are computed for pricing models.

Visualization
A bokeh and panel plot shows Model 1 vs Model 2 vs Model 3 prices over time.

▶️ How to Run:

Clone the repo:
git clone https://github.com/arya892004/summer-analytics-internship.git
cd realtime-parking-pricing

Set up the Python environment:
pip install pathway panel bokeh

Run the notebook:
jupyter notebook

At the end of the notebook, view the real-time pricing plot:

pn.Column(viz).servable()
📈 Output Example
Prices will dynamically range between ₹10–₹15/day depending on occupancy and context.

Report : [report of summer analytics program.docx](https://github.com/user-attachments/files/21104374/report.of.summer.analytics.program.docx)

