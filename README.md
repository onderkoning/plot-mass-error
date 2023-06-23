# plot-mass-error
For tandem mass spectrometry data (MS2) searched with Comet, plot the mass error

This describes how to install the software needed to create plots using the R script `plot-mass-error.R`, and how to run this script.
This script can only be used with search results of [Comet](https://uwpr.github.io/Comet/).

## Installation

Note: installation must be executed with root (Linux)/ Administrator (Windows) privileges.

* Install R from https://cran.r-project.org/ 
* Start R:
    ```
    cd "\Program Files\R\R-4.1.0"
    R
    ```
* Install standard R packages, install BioConductor and install MSnbase. From the R command prompt:
    ```R
    install.packages(c("stringr", "futile.logger", "optparse", "ggplot2", "gridExtra"))
    if (!requireNamespace("BiocManager", quietly = TRUE))
        install.packages("BiocManager")
    BiocManager::install(version = "3.14")
    BiocManager::install("MSnbase")
    ```

## Execution

After the above software is installed, plots can be generated by running from the command prompt:

```
Rscript plot-mass-error.R -e 0.01 -m 10 --outfile=recalplot --name="Mass error" somefile.mzid
```

Where option `-e` is the cutoff value for the Comet expect score and option `-m` is the maximum ppm error included in the plot,
and the final arguments are the mzID file of the data.

