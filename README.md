# Estimate weekly KDE ranges
Github repository: https://github.com/vee-jain/WeeklyKDE-MoveApps

## Description
Calculate KDE ranges at weekly intervals for your animals. Obtain the outputs of maps detailing their movements and plots showing changes in movement through time, with a focus on your animals' movements in the last week of the specified tracking period.

## Documentation
This app was developed for the 'EMAC23: Equip MoveApps for Conservation' with the intention to extract animals' weekly ranges to inform conservation management and monitoring actions. Once the data is thinned to a minimum of one minute resolution, it is segmented by weekly intervals per individual animal. 
Metrics are calculated on general movement features (e.g., straightness and cumulative distance traveled) per individual and week. Trends in movement patterns through time can inform whether animals are behaving differently (e.g., declining health or injury, migration, breeding). Note that NAs can be generated for metrics, but these are omitted for the rest of the code (refer to csv output).
For all individuals and weeks with more than 10 locations, the weekly KDE estimates at 0.50 and 0.95 isopleths are calculate and exported as plots and csv file. Note that if there are issues in the geometry (e.g., duplicated vertices), this is removed from the dataset for the remainder of the code.
Lastly, the gps fixes in the last week of tracking duration are intersected with the last week core area (0.50 isopleth) to obtain the number of fixes per time of day that the animal was in the core area. This is summarized on a weekly and daily basis, and can be used to make monitoring decisions based on the most recent data in the tracking period.

### Input data
MoveStack in Movebank format

### Output data
MoveStack in Movebank format

### Artefacts
(1)`data_track.csv` and (2)specific `map-id.html` in `map_html_files.zip`: tracking data (csv + leaflet-map-based html plots of individuals); 
(3)`track_list_df.csv` and (4)`metric_plots.pdf`: trends of seven movement metrics by week (csv + plots per individual); 
(5)`hr_plot.pdf`, (6)`hr_time_plots` and (7)`hr_df.csv`: weekly 0.50 and 0.95 KDE estimates (plots per individual and week + plots of KDE by week + csv);
(8)`last_week_pts_df.csv`: from the tracking period, the last week data points overall (csv) 
(9)`map_last_week_plot.html` in `map_html_files.zip`: last week data points intersected with KDE estimates (leaflet-map-based html plot)
(10)`time_in_core.csv`: last week data points in 0.50 core areas (csv); 
(11)`wk_time_core_plots.pdf` and (12)`day_time_core_plots.pdf`: histograms detailing the number of locations recorded at hours of the day in core areas per individual on a weekly and daily scale.

### Settings 

### Most common errors

### Null or error handling
NAs from movement metrics are omitted
For KDE estimation, issues in the geometry (e.g., duplicated vertices) are removed from the dataset

