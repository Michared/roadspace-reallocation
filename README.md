# roadspace-reallocation
Files for my 2024 MSc thesis evaluating the effects of road space reallocation on travel behavior using quantitative SD and Scenario Discovery. Files contained: <br>

<b>1_DataAnalysis</b> <br>
This directory contains the geospatial analysis and the other data analyses applied to data that needed further processing (e.g. to obtain the number of bike-sharing subscriptions per zone). It does not contain the raw geospatial data given these files are too large to upload to GitHub. Contents:<br>
<ul>
  <li><b>data</b> - directory with data files </li>
  <li><b>bikes.ipynb</b> - notebook processing bike subscription data</li>
  <li><b>jobs.ipynb</b> - noteboook processing job location data</li>
  <li><b>paris-roadspace.ipynb</b> - notebook processing overall public space distribution data</li>
  <li><b>pedestrian-space.ipynb</b> - notebook estimating pdestrian space </li>
  <li><b>paris-roadspace.ipynb</b> - notebook estimating total public space</li>
</ul> <br>

<b>2_ModelAndParameters</b> <br>
This directory contains the model file itself, the files that estimate the initial values of the stocks and constants in the model including sources used, the file that defines the effect lookups in the model, and the file that defines the uncertainty ranges. Contents:
<ul>
  <li><b>model.mdl</b> - the Vensim model file</li>
  <li><b>params.xlsm</b> - macro-enabled excel listing the majority of parameter estimates with links to the sources used, as well as the callibration of initial values to correctly initialize the modal split. the file contains seven tabs:
    <ul>
      <li>demography - this tab lists basic demographic data used to estimate stocks of the model (population, cars, homes) and reference migration and construction rates </li>
      <li>public space - this tab estimates initial values related to public space distribution and car parking </li>
      <li>reallocation policy - this tab extrapolates the proposed road space reallocation policy to define a desired public space distribution relative to the estimated current public space distribution  </li>
      <li>vehicle adoption - this tab estimates initial values related to bike and car adoption </li>
      <li>destination choice - this tab estimates the initial values for travel demand per spatial relation and per trip distance band, and defines the trip distance bands </li>
      <li>mode choice - this tab estimates the (initial) values for modal split, congestion, overcrowding, and travel speeds. It also computes the data for Figure 3.1 in the report. </li>
      <li>callibration - this tab callibrates the initial values of sets of parameters to match the modal split per trip distance band at initial time. </li>    
    </ul>
  </li>
  <li><b>lookups.xlsx</b> - excel file defining the fifteen effect variables and two scenario switches</li>
  <li><b>uncertainties.xlsx</b> - excel file documenting the uncertainty ranges in the model</li>
  <li><b>single_params.csv</b> - csv version of uncertainty ranges that can be used as an input for running the experiments with ema-workbench</li>  
</ul><br>

<b>3_Experiments</b> <br>
This directory contains the notebooks that run the experiments for scenario discovery, and the notebooks that cluster, visualize, and analyze the results from the experiments by applying PRIM. It also contains the image files for the plots. It does not contain the experiment results in data format  (results.tar.gz) given this file was too large to upload to GitHub. Contents:
<ul>
  <li><b>results</b> - directory containing the image files for the plots with experiment results</li>
  <li><b>run_experiments.ipynb</b> - notebook that runs the experiments while varying uncertain parameters (n=1000) and exports the results to a file named results.tar.gz</li>
  <li><b>PRIM_main_outcomes.ipynb</b> - notebook that clusters, visualizes and analyzes the main outcomes from the experiments (the reference mode, results included in the main text of the report)</li>
  <li><b>PRIM_other_outcomes.ipynb</b> - notebook that clusters and visualizes the other outcomes from the experiments (most of these results are included in the appendix rather than in the main text of the report)</li>
</ul><br>

<b>4_Miscellaneous</b> <br>
This directory contains the notebook that generated a map visualization in Chapter 3 and the notebook that reads the .mdl file to document the model parameters in the report's appendix.

