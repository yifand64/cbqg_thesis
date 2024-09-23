
# CBQG Thesis

Compositional analysis is one of the downstream analyses for scRNA-seq, it allows us to compare the composition of cellular heterogeneity between different conditions. However, the compositionality of the negative correlation and the sum-constrained makes most of the data assumption for univariate statistical tests invalid. Recently, there have been several compositional data analysis methods developed that claim to model the compositional data more accurately. Here, we benchmark 7 common methods for compositional data analysis and compute their false positive rate, statistical power, and their performance with low sample size. We found that the traditional methods had better performance in statistical power compared to Bayesian-based methods while they had similar performance in terms of false positive rate.

## Data Availability

Both data has been curated and the number of gene has been collapsed into compositional data of number of cells with cell type label, sample label, and condition label only. However, you can find both data from <a href="https://singlecell.broadinstitute.org/single_cell">Single Cell Portal</a> with their respective SCP number.

Two datasets were used for the benchmark of compositional analysis methods
1. An immune-cell signature of bacterial sepsis (**SCP548**)  
2. Impaired local intrinsic immunity to SARS-CoV-2 infection in severe COVID-19 (**SCP1289**)  

## Scripts
- `data_analysis.Rmd` contains the script to run each methods, this harmonizes the output from each methods as well.
- In the benchmark folder, the Rmd files correspond to each of the benchmarked criteria along with the output for 100 bootstrap iterations.
  1. `power.Rmd`: either removes Monocyte, adds DC cells, or converts NK to B cells to simulates the statistical power at detecting compositional change.
  2. `false_positive.Rmd`: randomly assigns half of the control condition to treatment to simulate a null dataset.
  3. `downsample.Rmd`: downsample % of cells to check for their statistical power at low sample size.
- In the figure folder, the `dataviz.Rmd` files will generate the figures using results from the benchmark folder while the `table.Rmd` generates the table.
