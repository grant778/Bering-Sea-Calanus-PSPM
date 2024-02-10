# Bering-Sea-Calanus-PSPM
R scripts and data used in Grant Woodard's 2023 Master's thesis "Climate Change and Density Dependence in the North Pacific: Applications to Salmon Run Forecasting and Plankton Population Dynamics".

Analyses performed in  R version 4.2.2 (2022-10-31)

MIT License

Copyright (c) 2024 grant778

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.



Use the NPRB versions of the model implementation scripts. The clean developed some bugs when I was removing some "unused and unecessary" code and I can't figure out how to delete them.

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
