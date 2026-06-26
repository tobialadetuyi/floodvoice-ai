# Data sources and links

This project combines multiple public and community data sources. Below are links and short notes for where to get each dataset.

1) NASA GPM (Global Precipitation Measurement)
- Website: https://gpm.nasa.gov/
- Notes: provides near-real-time rainfall estimates suitable for short-term flash-flood forecasting. Consider the TRMM/GPM IMERG products.

2) Sentinel-1 (Synthetic Aperture Radar)
- Copernicus Open Access Hub: https://scihub.copernicus.eu/
- Alternative access: AWS Public Datasets or Google Cloud Public Datasets
- Notes: SAR is very useful for detecting open-water extent under clouds.

3) Global Flood Awareness System (GloFAS)
- Website: https://www.globalfloods.eu/
- Notes: provides modelled river discharge and flood forecasts at global/regional scale. Useful as a complementary input or benchmark.

4) Google Earth Engine (optional)
- Website: https://earthengine.google.com/
- Notes: convenient for preprocessing and batch access to satellite imagery and derived indices.

5) Community river-gauge observations (USSD / IVR)
- Method: collect field observations via USSD forms, IVR calls, or WhatsApp reports
- Notes: these in-situ reports are noisy but provide important local validation and early warning triggers.

6) Local gauge networks and governmental hydromet data
- Contact national meteorological / hydrological services for public APIs or data-sharing agreements.

Usage tips

- Use multiple sources to reduce false alarms — fuse satellite + modelled + community reports.
- Preprocess satellite data to the spatial/temporal resolution the LSTM expects (e.g., hourly grids).

