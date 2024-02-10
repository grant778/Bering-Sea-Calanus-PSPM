# Bering-Sea-Calanus-PSPM
R scripts and data used in 2023 Master's thesis.

Use the NPRB versions of the script. The clean developed some bugs when I was removing some "unused and unecessary" code and I can't figure out how to delete them.

Bering_SST_12_06.xslx
  Bering SST temperature from NOAA physical sciences laboratory

Ikeda_2007_Respiration_Data.csv
  Copepod respiration data

  Ikeda, T., Sano, F., and Yamaguchi, A., 2007. Respiration in marine pelagic copepods: a global-
  bathymetric model. Marine Ecology Progress Series 339: 215-219
  Intergovernmental Panel on Climate Change (IPCC). 2014. Climate Change 2014: 
  Synthesis Report. Contribution of Working Groups I, II and III to the Fifth Assessment 
  Report of the Intergovernmental Panel on Climate Change.


Saiz_Calbert_2007_Calanus_Ingestion.csv
  Calanus Respiration data

  Saiz, E., and A. Calbet. 2007. Scaling of feeding in marine calanoid copepods. Limnology and 
  Oceanography 52: 487-921.


StageStructuredBiomass_GW_Calanus_max_ingestion_temp_dependent_V5_11_15_2023.R
  PSPM model structure is contained here. Required by model implementation scripts for them to run.

Parameter_Estimation.R

  Code detailing parameter estimation from Ikeda et al. 2007 and Saiz and Calbet 2007 data
  
Model_Implementation_1_NPRB.R

  Runs Basic PSPM model using parameters defined at top of code (or if using model defaults in     
  StageStructuredBiomass_GW_Calanus_max_ingestion_temp_dependent_V5_11_15_2023.R )

  This model 
  1. identifies a bifurcation point from the trivial equilibrium,
  2. uses the bifurcation point to find the non trival     
  equilibrium,
  3. then varies temperature at the nontrivial equilibrium to identify extinction temperature.
  4. Additionally it varies 
  size at maturity at the default temperature to assess changes in stage ratios.
  5. It also produces relevant graphs

Model_Impelemntation_2_NPRB.R

  Loops through first 3 steps of model 1 at varing sizes at maturity and saves the extinction temperature.
  Graphs temperature at extinction vs size at maturity.
