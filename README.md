# Delivery Exception & Late-Shipment Analysis

Analysis of delivery performance to find late shipments, identify what drives them, and prioritize exceptions for escalation, similar to the work of a transportation operations team.

## Dataset
"DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS" on Kaggle (uploaded by Shashwat Tiwari). The raw file has one row per order item, so it is grouped to one row per order (65,752 orders, January 2015 to January 2018). The dataset is not included in this repo because of its size; download it from Kaggle.

## Key findings
- 54.8% of orders (36,048) were delivered late.
- Late orders averaged 1.62 days of delay; 41.4% of late orders were delayed by 2+ days.
- Late rate by shipping mode: First Class 95.3%, Second Class 76.7%, Same Day 46.1%, Standard Class 38.1%.
- Late rates by region were similar (about 56 to 58% in the top regions), so shipping mode is the clearer driver than region.

## Exception queue
`exception_queue.csv` lists the 200 most delayed orders, with priority (High if delayed 3+ days, otherwise Medium) and a suggested escalation owner by region.

## Files
- `delivery_exception_analysis.ipynb`: full analysis in Python (pandas)
- `exception_queue.csv`: output exception queue

## Notes and limitations
- This is a public dataset; the very high late rate for First Class is worth investigating against real carrier SLAs, and may reflect how the dataset was built.
- Delay days = actual shipping days minus scheduled shipping days.

## Tools
Python (pandas, NumPy), Excel
