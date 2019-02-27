# GEM-MACH for CFFEPS #
Source code from Air Quality Research Division, Environment and Climate Change Canada (ECCC), Government of Canada

This is a modified version of the chemistry module code from version 2.1.0 of the ECCC GEM-MACH air quality model.  GEM-MACH is the model used in the ECCC operational air quality forecast system (e.g., Pavlovic et al., 2016) and this version has been modified to accept fire emissions from the [Canadian Forest Fire Emission Prediction System - CFFEPS](https://github.com/jackenvcan/cffeps).

The code posted here is the version of the GEM-MACH source code that was used in the study described in the manuscript entitled "The FireWork air quality forecast system with biomass burning emissions from the Canadian Forest Fire Emissions Prediction System" that was submitted to the journal [Geoscientific Model Development](https://www.geoscientific-model-development.net) in 2019.

GEM-MACH is an extension of ECCC's standard GEM numerical weather prediction model, a version of which is available from a [Github repository](https://github.com/mfvalin/gem). The executable for GEM-MACH is obtained by providing this chemistry library to GEM when generating its executable.

*Pavlovic, R., J. Chen, K. Anderson, M.D. Moran, P.-A. Beaulieu, D. Davignon, and S. Cousineau, 2016.  The FireWork air quality forecast system with near-real-time biomass burning emissions: Recent developments and evaluation of performance for the 2015 North American wildfire season.  J. Air & Waste Manage. Assoc., 66, 819-841, doi:10.1080/10962247.2016.1158214.*

---

Internal revision tracking: this is cloned from AQMAS/gem-mach repository branch *m3848_CFFEPS* from revision *AQMAS/gem-mach/commit/7eefc266c90739249ebad15a5d23bb1828ea449f*

