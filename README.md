# Crop-profile geographical analysis

This folder contains the final technical extension for the dissertation: a UKCEH-based crop-profile grid, exploratory agricultural-zone clustering, and zone-level comparison of model disagreement.

Main entry point:

```text
6_crop_profile_geography_colab.ipynb
```

The notebook is designed to run in Colab or a local geospatial Python environment. It should be run from top to bottom after setting the UKCEH Land Cover plus: Crops 2022 GeoPackage path.

## Purpose

The analysis asks whether the Sentinel-1 added value found in the model comparison varies across agricultural crop-composition zones.

It does not create a new crop map, and it does not treat UKCEH as ground truth. UKCEH Land Cover plus: Crops 2022 is used as a secondary benchmark/product layer for crop-area aggregation.

## Expected workflow

1. Load UKCEH Land Cover plus: Crops 2022.
2. Harmonise crop names to the eight dissertation classes.
3. Build a 10 km British National Grid over East Anglia.
4. Intersect crop polygons with grid cells.
5. Calculate crop area and crop proportions per grid cell.
6. Filter low selected-crop-area cells.
7. Run k-means clustering and silhouette checks.
8. Map crop-profile zones.
9. Join matched model disagreement points to crop-profile zones.
10. Summarise S2 disagreement, S1+S2 disagreement, SAR reduction and CROME-UKCEH disagreement by zone.
11. Optionally export HTML maps for exploration.

## Expected outputs

Tables:

- `outputs/tables/crop_profile_grid_area_table.csv`
- `outputs/tables/crop_profile_grid_proportion_table.csv`
- `outputs/tables/crop_profile_grid_filter_summary.csv`
- `outputs/tables/crop_profile_cluster_silhouette_scores.csv`
- `outputs/tables/crop_profile_cluster_centroids.csv`
- `outputs/tables/zone_level_model_disagreement.csv`
- `outputs/tables/zone_level_crome_ukceh_disagreement.csv`

Geospatial outputs:

- `outputs/geo/crop_profile_grid.gpkg`
- `outputs/geo/crop_profile_grid_with_clusters.gpkg`
- `outputs/geo/model_points_with_crop_profile_zone.gpkg`

Figures:

- `outputs/figures/selected_crop_intensity_map.png`
- `outputs/figures/crop_profile_cluster_map.png`
- `outputs/figures/crop_profile_silhouette_scores.png`
- `outputs/figures/zone_level_sar_reduction_bar.png`

HTML maps:

- `outputs/maps/crop_profile_cluster_map.html`
- `outputs/maps/selected_crop_intensity_map.html`
- `outputs/maps/zone_level_sar_reduction_map.html`

Notes:

- `docs/crop_profile_geography_notes.md`
- `outputs/logs/crop_profile_run_manifest.json`

