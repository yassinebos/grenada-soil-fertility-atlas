# Metadata

This directory contains metadata describing the GeoTIFF files included in the Grenada Soil Fertility Atlas (GSFA) dataset.

## Dataset overview

The dataset provides high-resolution (30 m) prediction and uncertainty maps for seven soil fertility indicators at two soil depths (0–30 cm and 30–50 cm) across the agricultural lands of Grenada.

The maps were generated using Random Forest models trained on field soil observations and environmental covariates. Prediction uncertainty was estimated using the standard deviation of ten bootstrap prediction replicates.

## Directory structure

```
Prediction_maps/
├── 0_30cm/
└── 30_50cm/

Uncertainty_maps/
├── 0_30cm/
└── 30_50cm/
```

Prediction maps contain the estimated values of each soil property.

Uncertainty maps contain the standard deviation of predictions obtained from ten bootstrap model repetitions.

---

## Soil variables

| Variable | Description | Unit |
|----------|-------------|------|
| P | Available phosphorus | ppm (mg kg⁻¹) |
| K | Exchangeable potassium | ppm (mg kg⁻¹) |
| Mg | Exchangeable magnesium | ppm (mg kg⁻¹) |
| Ca | Exchangeable calcium | ppm (mg kg⁻¹) |
| Fe | Available iron | ppm (mg kg⁻¹) |
| pH | Soil pH | pH units |
| CEC | Cation exchange capacity | meq/100 g |

---

## Raster characteristics

| Property | Value |
|----------|-------|
| File format | GeoTIFF (.tif) |
| Coordinate reference system | EPSG:32620 (WGS 84 / UTM Zone 20N) |
| Spatial resolution | 30 m |
| Data type | Float32 |
| Compression | LZW |
| NoData value | NA |

---

## Naming convention

Prediction maps follow the naming convention:

```
<Variable>_<Depth>_prediction.tif
```

Examples:

```
P_0_30cm_prediction.tif
CEC_30_50cm_prediction.tif
```

Uncertainty maps follow the naming convention:

```
<Variable>_<Depth>_uncertainty.tif
```

Examples:

```
P_0_30cm_uncertainty.tif
CEC_30_50cm_uncertainty.tif
```

---

## Uncertainty estimation

Prediction uncertainty was estimated using a bootstrap approach.

For each soil property, the Random Forest model was fitted ten times using bootstrap resampling of the calibration dataset. The uncertainty maps represent the pixel-wise standard deviation of the predictions obtained from these ten bootstrap model runs.

Higher values indicate greater model uncertainty.

---

## Data usage

The prediction maps represent the estimated spatial distribution of soil properties and should be interpreted together with the corresponding uncertainty maps.

Users are encouraged to consider uncertainty values when supporting soil fertility assessment, agricultural management, or spatial analyses.

---

## Citation

If you use this dataset, please cite both:

1. the accompanying publication (to be added after publication);
2. the Zenodo dataset DOI (to be added after publication).

---

## License

This dataset is distributed under the Creative Commons Attribution 4.0 International (CC BY 4.0) License.
