# CalFire Data in QGIS

1. **Open the QGIS Project:**
   - Launch QGIS.
   - Navigate to `File` > `Open Project`.
   - Browse to and select the `Fire_Data.qgz` project file. This project includes two key layers: `fire22_1 — firep22_1` for CALFIRE wildfire perimeters and `CA_POP_HOUSING_TRACTS_fixed` for California census tracts data.

2. **Filter the CALFIRE Perimeter Layer:**
   - In the Layers Panel, right-click on the `fire22_1 — firep22_1` layer.
   - Choose `Filter...` from the context menu.
   - Enter the following expression to filter for fires in 2020 that burned more than 10,000 acres: `"YEAR" = 2020 AND "GIS_ACRES" > 10000`.
   - Click `OK` to apply the filter.

3. **Select Census Tracts Intersecting with Filtered Fire Perimeters:**
   - Go to `Vector` > `Research Tools` > `Select by Location...`.
   - In the Select by Location dialog, set the following:
     - For `Select features in`: choose `CA_POP_HOUSING_TRACTS_fixed`.
     - For `that intersect features in`: choose the filtered `fire22_1 — firep22_1` layer.
   - Ensure the geometric predicate `intersect` is checked.
   - In the Advanced Settings, check the option to Ignore Damages Geometries
   - Click `Run` to execute the selection. This selects census tracts that intersect with the fire perimeters from 2020 fires larger than 10,000 acres.

4. **Generate Summary Statistics for Affected Housing Units and Population:**
   - With the `CA_POP_HOUSING_TRACTS_fixed` layer still selected, navigate to `Vector` > `Analysis Tools` > `Basic Statistics for Fields`.
   - In the Basic Statistics dialog, select `CA_POP_HOUSING_TRACTS_fixed` as the Input layer.
   - Choose `TTLHOUSING` for the first run to calculate statistics on the total number of housing units affected, then repeat the process with `TTLPOP` for the total population affected.
   - Click `Run` for each attribute to generate the summary statistics.

By following these steps, participants will identify and explore the impact of significant 2020 wildfires on housing and population within California census tracts.
