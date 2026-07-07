# Crop-profile geography notes

Date run: 2026-07-07 16:12

## Purpose

This analysis uses UKCEH Land Cover plus: Crops 2022 to create 10 km crop-profile grid cells, cluster them into agricultural crop-composition zones, and examine whether Sentinel-1 SAR disagreement reduction varies by zone.

## Setup

- UKCEH source: `/content/drive/MyDrive/Dissertation/ukceh_east_anglia/lccm-2022_6395063/lccm-2022_6395063.gpkg`
- Grid size: 10,000 m
- Minimum selected-crop area threshold: 500 ha
- Retained grid cells for clustering: 144
- Chosen number of clusters: 4
- Reference framing: UKCEH is used as a secondary crop-map product, not direct ground truth.

## Key outputs

- Crop-profile area/proportion tables: `outputs/tables/crop_profile_grid_area_table.csv` and `outputs/tables/crop_profile_grid_proportion_table.csv`
- Cluster centroids: `outputs/tables/crop_profile_cluster_centroids.csv`
- Zone-level model disagreement: `outputs/tables/zone_level_model_disagreement.csv`
- Static dissertation figures: `outputs/figures/selected_crop_intensity_map.png`, `outputs/figures/crop_profile_cluster_map.png`, `outputs/figures/zone_level_sar_reduction_bar.png`
- Optional HTML maps: `outputs/maps/`

## Initial interpretation

Use the cluster centroid table to name agricultural zones cautiously. The zone-level disagreement table should be used to test whether SAR disagreement reduction is larger in zones associated with potatoes, beet, maize or pulses than in cereal-dominant zones. Small-sample zones should be treated as descriptive only.

The largest observed SAR disagreement reduction is in cluster 3, with reduction 0.084 across 359 matched test samples.
