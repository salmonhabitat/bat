bat - an ArcGIS addon
====

Overview
---

Descriptive stat metrics for stream barriers.  Creates *Functional networks*

- Merge output from multiple scenarios
- Residual effects
- Identify closest US/DS barriers

**Requires shapefiles. Can't use GDB.**

- Shapefile tolerance is an issue. Before starting, import to GDB, then re-export to Shapefile in order to get around shapefile intolerance issues.
- Data should be in a projected, meter-based coordinate system, not geographic system.

BAT Toolbar
----------

Coordinate system must be in meters, unique polylines. Will calculate from/to nodes unless already present. Single channel networks, + connected.a

1. Create a scenario
  - requires .shp
  - polyline id's must be unique
  - require from/to nodes (NHD+ should already have these, but good practice to recalculate them)
  - Regions, (HUC4 is usually good, and respect watershed boundaries.)
  - No loops, and no multi-threaded sections. (Braids need to be removed...)

2. Data preparation
  - Prebuild and share some of these networks?
  - NHD+ has been completed at the 100k scale. NHDH+ (24K) currently in the works. **Jed uses the 24k.**a
  - **Snap points**. Set tolerance low, (1, 2m)
  - **Core Metrics** - distance, up/down barriers, connected lengths, absolute/relative gains for fish, & barrier densities

3. Outputs
  - Prioritize barriers
  - Describe watershed connectivity/fragmentation

Joining
----------

Spatial join centroids to the functional networks.
