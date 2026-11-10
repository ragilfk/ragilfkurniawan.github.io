# Ragil Faiz Kurniawan

BSc in Environmental Sciences at Wageningen University (WUR).  
I look at Climate, Earth, and Environmental systems through a physical lens—focusing on mass and energy balances, process-based modeling, and land–water–atmosphere dynamics.

---

### Featured Project: Wet or White Winter in the Netherlands? (DJF 2026–2027)

Every Dutch winter balances between mild, rainy Atlantic westerlies (**Wet**) and freezing, dry continental easterlies (**White**). 

This pipeline processes 51 ensemble members from the **ECMWF SEAS5** seasonal forecast model via Copernicus CDS, area-weights the signal over the Netherlands, and calibrates the distribution against **30 years of KNMI ground data from De Bilt (1991–2020)**.

* **Wet Threshold:** DJF precipitation $> 215\text{ mm}$ (historical median rainfall).
* **White Threshold:** DJF snowfall liquid equivalent $> 18\text{ mm}$ (~15–20 cm uncompacted snow).

[ECMWF SEAS5 (51 Members)] ──> [NL Cosine Area-Weighting] ──> [KNMI 1991–2020 Calibration] ──> [P(Wet) vs P(White)]


#### Outputs
* `netherlands_winter_2026_2027_assessment.png` — Synoptic Atlantic storm tracks, $0^\circ\text{C}$ isotherms, and raw ensemble scatter.
* `seas5_calibrated_validation_assessment.png` — Mean-and-variance calibrated probabilities vs. the 33.3% climatological baseline.

#### Run
```bash
pip install cdsapi xarray netcdf4 numpy scipy matplotlib cartopy shapely
python run_seas5_winter_pipeline.py
