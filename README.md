# Set up
The program was developed in R 4.1.2 with an R package “openxlsx” which could be installed by

```r
if(!require(openxlsx)){
  install.packages("openxlsx")
}
```

The program can be loaded in R with either
```r
source("FileName/CODESNAME.R")
```
or
```r
source_url("GITHUBLINK/CODESNAME.R")
```

# Introduction
Measurements in each table were extracted separately and then merged into a “wide format” data file since the EOS outputs were composed of multiple tables with different structures. 
The EOS2 program works by first locating table headers and subsequently scanning the entire table and transforms the loaded data into one observation, in the output result file. Any empty cells, or missing values, in the EOS Advanced Spine Workflow .xlsx file were skipped  . Separate measures in the output file can be identified using the unique patient ID and EOS scan date.

