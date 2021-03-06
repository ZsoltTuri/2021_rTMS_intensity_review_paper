# Selecting stimulation intensity in repetitive transcranial magnetic stimulation studies: A systematic review between 1991 and 2020
Code and raw data for our paper "Selecting stimulation intensity in repetitive transcranial magnetic stimulation studies: A systematic review between 1991 and 2020"

If you want to use this data/analysis in a research publication, please cite [our paper](https://pubmed.ncbi.nlm.nih.gov/33754397/).

Here, you can find the [preprint](https://www.biorxiv.org/content/10.1101/2020.09.28.316190v1) of the paper.

## Citation
Turi Z, Lenz M, Paulus W, Mittner M, Vlachos A. Selecting stimulation intensity in repetitive transcranial magnetic stimulation studies: A systematic review between 1991 and 2020. Eur J Neurosci. 2021 May;53(10):3404-3415. doi: 10.1111/ejn.15195. Epub 2021 Apr 10. PMID: 33754397.

~~~{bibtex}
@article{turi2021selecting,
  title={Selecting stimulation intensity in repetitive transcranial magnetic stimulation studies: A systematic review between 1991 and 2020},
  author={Turi, Zsolt and Lenz, Maximilian and Paulus, Walter and Mittner, Matthias and Vlachos, Andreas},
  journal={Eur J Neurosci},
  volume={53},
  number={10},
  pages={3404--3415},
  year={2021},
  publisher={Wiley-Blackwell}
}
~~~

## License 

The content of the repository is licensed under a Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0), 
which permits non-commercial use, sharing, adaptation, distribution and reproduction in any medium or format, 
as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons license, and indicate if changes were made.

## Requirements

Analysis are coded in [R](http://r-project.org). 
A moderate amount of R-packages are required listed in docs/sessionInfo.txt. 

## Setup

This repository uses the
[ProjectTemplate](http://projecttemplate.net/) directory layout. 

## Data

Raw data is located in `data/raw` and is provided in `.xlsx` format.

The `.R` scripts located in `data` load the raw files into `R` workspace.

Relevant variables are coded as follows:

* `pdf_name` - format: firstAuthor_yearOfPublication_journal_pubmedID
* `typ` - type of rTMS
	- rTMS: conventional rTMS (e.g., 1 Hz, 10 Hz, etc.)
	- iTBS: intermittent theta burst stimulation
	- cTBS: continuous theta burst stimulation 
	- QPS: quadripulse stimulation
* `frq` - intraburst frequency 
* `si_app` - stimulation intensity selection approach 
	- AMT: active motor threshold
	- RMT: resting motor threshold
	- MT: unspecified motor threshold
	- FL: functional lesion
	- PT: phosphene threshold
	- FXD: fixed intensity
	- EF: electric field
* `th_strat` - threshold-estimation strategies 
	- ML: method of limit
	- 5STEP: 5 step procedure
	- TH: threshold hunting
	- MLTH: maximum likelihood based threshold hunting
	- PEST: parameter estimation by sequential testing
	- MTAT: TMS Motor Threshold Assessment Tool
* `th_meas` - threshold measurement 
	- E: electrode
	- V: visual
* `mt_uV` - amplitude of the motor evoked potential in microvolt 
* `th_ri` - threshold ratio (e.g., 3_6: 3 out of 6)
* `mt_contr` -percentage or the amplitude of the motor threshold contraction (e.g., 10%-10% of the maximum contraction)
* `si_pct` - percent of stimulation intensity
* `si_pct_min` - percent of stimulation intensity (min value)
* `si_pct_max` - percent of stimulation intensity (max value)
* `mso` - maximum stimulator output
* `stim_co` - stimulator company
* `stim_mo` - stimulator model
* `coil_shp` - coil shape
* `coil_siz` - coil size
* `coil_mo` - coil model
* `note` - note
* `contrib_id` - contributor id


## Analyses

All analyses are located in `src/`. To run the scripts, you need to
have the `ProjecTemplate` package and various other packages
installed.

The first two lines in each file
~~~{R}
library(ProjectTemplate)
load.project()
~~~
convert the raw data into a more convenient format by

1. running the `data/<dataset>.R` file
2. running the preprocessing scripts in `munge`
