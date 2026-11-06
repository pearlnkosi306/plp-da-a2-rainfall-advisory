# Rainfall Analysis and Planting Advisory

**Author:** Buhle Pearl Nkosi · 1MillionDevsCohort Data Analytics

## Project Summary

A farmer-support NGO sends SMS advice on planting windows in five Kenyan counties (Nairobi, Nakuru, Kisumu, Mombasa, Machakos). The Machakos station data was typed by hand and contained invalid readings, so I cleaned it first (two months imputed with the rounded mean of the valid readings), combined all counties into a 5 × 12 NumPy array, and used NumPy axis operations, boolean masks and `argmax` to find annual totals, wettest months, dry-month counts and the best two-month planting window per county. The results are saved in `rainfall_summary.csv`.

## Files

- `rainfall_analysis.ipynb`: full analysis with outputs, including the "Planting Advisory" and "Data Quality Notes" sections
- `rainfall_summary.csv`: one row per county (`county`, `annual_total_mm`, `wettest_month`, `dry_months`, `planting_window`)
- `requirements.txt`: Python libraries used

## How to Run

1. Open `rainfall_analysis.ipynb` in Google Colab (or Jupyter locally).
2. Select Runtime → Restart and run all.
3. The notebook rewrites `rainfall_summary.csv` in the same folder.

Locally: `pip install -r requirements.txt`, then open the notebook in Jupyter.

## Planting Advisory

- Farmers in Nairobi, Nakuru, Kisumu and Mombasa should plant in April to May, the wettest two-month window in all four counties, while Machakos farmers should plant in November to December.
- Kisumu is the most reliable county (no dry months, 1,371 mm a year) and Machakos is the riskiest (six dry months, 811 mm a year), so short-season crops are advised in Machakos.
- Caveat: two Machakos readings (April and September) were invalid and were estimated at 68 mm, and each county is one station for one year, so treat these windows as a starting point and check them against local forecasts.
