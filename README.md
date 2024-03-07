# Biomass_prototype
## Ethiopia Rangeland Forage Prediction Model

### Background
This repository hosts the development of a prototype forage prediction model specifically tailored for the rangeland areas of Ethiopia. The Ethiopian rangelands predominantly consist of shrubs and grasslands, defining them as pastoral zones.

### Data Preparation
The model utilizes datasets including Normalized Difference Vegetation Index (NDVI) from VIIRS, Total Precipitation (PTOT) from CHIRPS, and Soil Moisture (SM) from NASA Soil Moisture Active and Passive (SMAP). A mesh grid of 5 sq.km was established over the rangeland, with pixel values extracted using Google Earth Engine. These datasets were preprocessed and cleaned to ensure optimal model performance.

### Model Development
Geographically Weighted Regression (GWR) serves as the foundation for developing the prototype rangeland feed prediction model. The model is represented by Equation 1:

\[ Y_i = \alpha(U_i,V_i) + \beta(U_i,V_i)X_i + \lambda(U_i,V_i)Z_i \]

Where \( U_i \) and \( V_i \) denote the coordinates of location \( i \), while \( \alpha \), \( \beta \), and \( \lambda \) represent local parameters to be estimated at location \( i \). \( X \) and \( Z \) denote independent variables.

The output from the prediction model is converted to pasture biomass using Equation 2:

\[ \text{Pasture biomass} = (6480.2 \times \text{Prediction}) - 958.6 \]

This technique, as described in Hobbs (1995), yields output in Kg/ha, subsequently converted to tonnes per hectare (t/ha) where 1 t/ha equals 1000 kg/ha.

### References
- Georganos, S., Grippa, T., Vanhuysse, S., Linard, C., Wolff, E., & Vansteenkiste, T. (2017). Geographically Weighted Regression and its Application in the Environmental Sciences. Environmental Modelling & Software, 91, 126-166.
- Hobbs, N. T. (1995). Modification of Ecosystems by Ungulates. The Journal of Wildlife Management, 59(4), 695-713.
