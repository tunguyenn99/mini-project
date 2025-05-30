# 📦 Failed Order Analysis – Gett Platform (Mini Project)

This mini-project is based on a **case study** shared in the [Xóm Data - Cùng học Data Analyst / Data Engineer / Data Scientist](https://www.facebook.com/groups/1707916343455196). The objective is to explore and analyze **failed ride-hailing orders** from Gett (formerly known as GetTaxi), a B2B ground transportation management platform.

---

## 📟 Problem Overview

When a customer clicks the **Order** button on the app, the system attempts to match them with a suitable driver. However, not all requests are successful.

This project focuses on analyzing orders that **failed**, including:

- Orders canceled by the customer (before or after driver assignment)
- Orders rejected by the system or drivers
- Reasons and patterns behind failed matches

---

## ✅ Task Requirements

Your task is to complete the following:

1. 📊 **Distribution of failure reasons**
   - Visualize the count of orders by failure reason:
     - Canceled before assignment
     - Canceled after assignment
     - Rejected by system/driver
   - Identify the most common failure type and analyze why.

2. 🕒 **Hourly distribution of failed orders**
   - Plot failures by hour of the day.
   - Are there hours with unusual failure rates?
   - What time of day sees the most failures? Explain possible reasons.

3. ⏱ **Cancellation time analysis**
   - Visualize average time to cancel (with and without assigned driver), broken down by hour.
   - What patterns do you observe?

4. 🚕 **ETA analysis**
   - Visualize average **ETA (estimated time of arrival)** per hour.
   - What insights can be drawn from this distribution?

5. 🗘️ **BONUS – Spatial Hexagon Mapping**
   - Use `h3` and `folium` to:
     - Determine how many **size 8 hexes** contain **80% of all orders**.
     - Visualize these hexes on a map, colored by number of failed orders.

---

## 📂 Dataset Description

You are provided with two CSV files: `data_orders.csv` and `data_offers.csv`.

### `data_orders.csv`

| Column Name                | Description |
|---------------------------|-------------|
| `order_datetime`          | Timestamp of order |
| `origin_longitude`        | Longitude of origin |
| `origin_latitude`         | Latitude of origin |
| `m_order_eta`             | Estimated time until arrival (ETA) |
| `order_gk`                | Order ID |
| `order_status_key`        | Order status: <br/>`4` = customer cancelled, `9` = system rejected |
| `is_driver_assigned_key`  | Was a driver assigned? (1 = Yes, 0 = No) |
| `cancellation_time_in_seconds` | Seconds until cancellation |

### `data_offers.csv`

| Column Name | Description |
|-------------|-------------|
| `order_gk`  | Order ID (foreign key to `data_orders`) |
| `offer_id`  | Unique offer ID (proposal to a driver) |

---

## 🔧 Setup & Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/gett-failure-analysis.git
   cd gett-failure-analysis
   ```

2. (Optional) Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install all dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## 🛠 Requirements

Dependencies are managed using `requirements.txt`. To install:

```bash
pip install -r requirements.txt
```

To regenerate or update it based on your current environment:

```bash
pip freeze > requirements.txt
```

---

## 🧽 Bonus Notes

- This project includes geospatial analysis with `h3` and `folium`, which may require additional setup (e.g., Jupyter extensions).
- Code is modularized by notebook or script for each task.

---

> 📬 Contributions or questions? Feel free to reach out or comment on the original post on Facebook.
