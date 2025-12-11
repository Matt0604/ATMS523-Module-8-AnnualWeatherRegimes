# ATMS523-Module-8-AnnualWeatherRegimes
This repository is to satisfy my semester project for ATMS 523 at the University of Illinois Urbana-Champaign. Here, a set of year-long weather regimes (WRs) are created over the CONUS, setting the foundation for future research towards my Ph.D. dissertation. WRs are created using K-means clustering analysis of 5 clusters.

# Overview
The Kmeans code contains the Kmeans clustering analysis for creating year-long weather regimes for 1990-2024. The anomalies are detrended by detrending the annual linear trend, and normalizing by the 60-day centered running mean to account for seasonality. This way, the summer anomalies matter just as much as the winter anomalies and the WR structures are not biased towards winter structures. An EOF filter was then applied to account for 90% of the variance via the first 8 EOFs. The Davies-Bouldin index was used to determine that the optimal structures is 5. The 5 structures identified all look like normal everyday upper-air atmospheric circulation patterns. 
The modeling code uses the Graber et al. 2025 methodology emphasizing weather regime frequency, tornado probabilities, and persistence. This is done for tornado days and tornado outbreaks. Model skill is much better for tornado outbreaks, which makes sense given that outbreaks depend on specific synoptic scale circulation patterns (Cwik et al. 2022). 
The labels.npy file is the the weather regime labels (0-4 representing WRs A-E) in order from the first day to the last day. The WR_structures.npy file is the saved, normalized weather regime structures that are plotted in the Kmeans python notebook. The annualcounts.npy are the annual frequencies of the 5 weather regimes with A listed first, B listed second, and so on. 

# Future Work
Thus far, the methodology mostly matches my previous work with the exceptions of the actions that I take to account for seasonality. It is possible that more actions will have to be taken for the year-long WR framework that I have not yet considered, which may improve model skill for tornado days. I may want to use my previous WRs as bases to derive the year-long WRs as a means to maintain robustness between my studies. 

# References
Cwik, P., McPherson, R. A., Richman, M. B., and Mercer, A. E.: Climatology of 500-hPa Geopotential Height Anomalies Associated with May Tornado Outbreaks in the United States, Int. J. Climatol., 43, 893–913, https://doi.org/10.1002/joc.7841, 2022.

Davies, D. L. and Bouldin, D. W.: A Cluster Separation Measure, IEEE Trans. Pattern Anal. Mach. Intelligience, PAMI-1, 224–227, https://doi.org/10.1109/TPAMI.1979.4766909, 1979.

Graber, M., Wang, Z., and Trapp, R.: Linking weather regimes to the variability in warm-season tornado activity over the United States, Weather Clim. Dynam., 6, 807-816, https://doi.org/10.5194/wcd-6-807-2025, 2025

Grams, C. M., Beerli, R., Pfenninger, S., Staffell, I., and Wernli, H.: Balancing Europe’s Wind-power Output through spatial development informed by weather regimes, Nat. Clim. Change, 7, 557–562, https://doi.org/10.1038/nclimate3338, 2017.

Hersbach, H., Bell, B., Berrisford, P., Hirahara, S., Horányi, A., Muñoz‐Sabater, J., Nicolas, J., Peubey, C., Radu, R., Schepers, D., Simmons, A., Soci, C., Abdalla, S., Abellan, X., Balsamo, G., Bechtold, P., Biavati, G., Bidlot, J., Bonavita, M., De Chiara, G., Dahlgren, P., Dee, D., Diamantakis, M., Dragani, R., Flemming, J., Forbes, R., Fuentes, M., Geer, A., Haimberger, L., Healy, S., Hogan, R.J., Hólm, E., Janisková, M., Keeley, S., Laloyaux, P., Lopez, P., Lupu, C., Radnoti, G., de Rosnay, P., Rozum, I., Vamborg, F., Villaume, S., Thépaut, J-N. (2017): Complete ERA5: Fifth generation of ECMWF atmospheric reanalyses of the global climate. Copernicus Climate Change Service (C3S) Data Store (CDS). (Accessed on 25-09-2025)

Lee, S. H., Tippett, M. K., and Polvani, L. M.: A New Year-Round Weather Regime Classification for North America, J. Climate, 36, 7091–7108, https://doi.org/10.1175/JCLI-D-23-0214.1, 2023.


