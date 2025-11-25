# Flight Delay and Airline Performance Dashboard (Power BI)

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Analytics-yellow)
![DAX](https://img.shields.io/badge/DAX-Functions-blue)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-380K%20Records-green)
![Excel](https://img.shields.io/badge/Excel-Data%20Prep-lightgrey)
![Python](https://img.shields.io/badge/Python-Used%20for%20Preprocessing-blueviolet)
![License](https://img.shields.io/badge/License-MIT-brightgreen)
![Stars](https://img.shields.io/github/stars/vikrantthenge/https://github.com/Vikrantthenge/Flight-Delay-Airline-Performance-Dashboard-Power-BI-/blob/main/README.md?style=social)


---

## Project Overview

This project analyzes approximately 380,000 US flight records to understand delays, cancellations, airport bottlenecks, and airline performance.  
The dashboard uses Power BI, Power Query, and DAX to uncover operational insights that matter for decision-makers and operations teams.

The report is organized into three analytical pages:

1. Executive Summary  
2. Airport Performance  
3. Airline (Carrier) Performance  

---

## Page 1 – Executive Summary

### KPIs
- Total Flights  
- On-Time Percentage  
- Average Departure Delay  
- Cancellation Rate  
- Total Delayed Flights  

### Visuals
- Delay Cause Breakdown  
- Monthly Average Departure Delay  
- Monthly Delayed Flights  
- Top 10 Worst Routes  

Purpose: A high-level view of operational performance across airports, routes, and airlines.

---

## Page 2 – Airport Performance

### KPIs
- Total Flights  
- On-Time Percentage  
- Average Departure Delay  
- Cancellation Rate  

### Visuals
- Delayed Flights by Origin Airport  
- Average Departure Delay by Airport  
- Cancellation Rate by Airport  
- ORIGIN → DEST Flight Volume Heatmap  

Purpose: Identify underperforming airports and bottleneck locations.

---

## Page 3 – Airline Performance

### KPIs
- Total Flights  
- On-Time Percentage  
- Average Departure Delay  
- Cancellation Rate  

### Visuals
- Total Delayed Flights by Airline  
- Average Departure Delay by Airline  
- Cancellation Rate by Airline  
- Airline Performance Summary Table  

Purpose: Compare airline reliability and punctuality using data-driven KPIs.

---

# Data and Transformations

Dataset: US Flight Delay and Cancellation Data (~380k rows)

### Columns used
FL_DATE, ORIGIN, DEST, AIRLINE, DEP_DELAY, CANCELLED, and multiple delay cause fields (weather, NAS, carrier, late aircraft, security).

---

## Calculated Columns (DAX)

```DAX
Route = 'flights'[ORIGIN] & " → " & 'flights'[DEST]

OnTimeFlag = IF('flights'[DEP_DELAY] <= 0, 1, 0)

CancelledFlag = IF('flights'[CANCELLED] = 1, 1, 0)
