# Crop-profile geography method notes

Use these notes when writing the dissertation Methods/Results after the notebook has run.

## Framing

This analysis extends the core S2-only versus S1+S2 model comparison by asking whether SAR added value varies by agricultural context. The agricultural context is represented as a crop-composition profile for each 10 km grid cell.

UKCEH Land Cover plus: Crops 2022 is used for area/proportion aggregation because it is a polygon crop product with crop names and area-bearing geometries. It should be described as a secondary crop-map product or benchmark layer, not as direct ground truth.

## Unit of analysis

The preferred unit is a regular 10 km British National Grid cell. For each retained grid cell, the analysis calculates the area and proportion of the eight dissertation crop classes:

1. Winter wheat
2. Winter barley
3. Spring barley
4. Beet (sugar beet / fodder beet)
5. Maize
6. Oilseed rape
7. Potatoes
8. Pulses / field beans and peas

Cells with very small selected-crop area should be filtered before clustering, because their crop proportions may be unstable or dominated by edge effects.

## Clustering

K-means clustering is used as an exploratory grouping method, not as an official agricultural zoning method. Silhouette scores help choose a plausible cluster count, but the final `k` should also be interpretable from the centroid table.

Cluster labels should be descriptive and derived from the centroid values, for example cereal-dominant, root-crop-associated, mixed spring-crop or maize/pulses-associated. Do not force labels that are not supported by the centroid table.

## Model-disagreement join

Matched model test points are spatially joined to the crop-profile zones. For each zone, report:

- number of matched test samples;
- S2 disagreement rate;
- S1+S2 disagreement rate;
- SAR disagreement reduction;
- CROME-UKCEH disagreement rate where UKCEH labels are available.

Small-sample zones should be interpreted cautiously.

## Dissertation interpretation

The strongest dissertation result would be a table showing whether SAR reduction is larger in zones associated with potatoes, beet, maize or pulses than in cereal-dominant zones. This directly links the crop-profile analysis back to the main research question.

Interactive HTML maps are useful for inspection, but the assessed dissertation must include static figures/tables and written interpretation.

