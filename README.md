# Setup
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
CODESNAME is used to extract measurements and numerical values from the .xlsx file from the Advanced Spine Workflow data included with each EOS spine scan. Within each .xlsx file, measurements in each table were extracted separately and then merged into a “wide format” data file since the EOS outputs were composed of multiple tables with different structures. Users can perform the data aggregation as follows:

## EOS File Preparation
To use the CODESNAME, all EOS files for the Advanced Spine Workflow of each patient should be saved in one folder named by the numerical patient ID, to include leading zeros.  Then, all the associated files (i.e., .docx, .xslx, DICOM images) for each EOS spine scan for a patient should be located within a subfolder, located within each patient folder, and should be created with the EOS spine scan date using the “MM-DD-YYYY” format. 

The result should be that all files associated with each EOS spine scan for a patient has its own folder, named using the date, and these are all stored within the main folder for each patient, named using the numerical patient ID (Figure 1).  Further, all patient folders for extraction should be saved within one parent folder, for example, “Test Data” as shown in Figure 1. The parent folder should not contain any other files, data, or subfolders which are not obtained from the EOS spine scan Advanced Workflow.  Empty folders should also not be saved within the parent folder. 

![Figure 1](GITHUBLINK)

## Data Aggregations
This program would direct the users to specify the parent folder where the user has saved all reports, and the output folder file path where users would like the aggregated data to be saved. It is notable that the output folder should be outside of the parent folder. Once the input and output file locations have been specified, the program would aggregate all data into a single file “MergedData_YYYYMMDD.xlsx” in the assigned output folder, where the “YYYYMMDD” corresponds to the date that the CODESNAME was run.  

## Results
The aggregated data were color coded by patient information (Patient ID and Visit date, specified by the folder names). Collected measurements were renamed using the abbreviation of the EOS Advanced Spine Workflow .xlsx file table headers as below. Specifically, PP indicates “Patient Plane” and RP means “Radio Plane”.

Tables | Variable Names | Measurements
--- | --- | ---
Basic Information | Patient ID | Patient ID, pecified by the folder names
--- | Visit Date | Visit date, specified by the folder names
Scoliosis parameters | LumbarCobb | Cobb angle of lumbar scoliosis parameters
--- | LumbarApex | Axial rotation of apical vertebra lumbar scoliosis
--- | MainCobb | Cobb angle of main scoliosis parameters
--- | MainApex | Axial rotation of apical vertebra main scoliosis
--- | ProximalCobb | Cobb angle of Proximal scoliosis parameters
--- | ProximalApex | Axial rotation of apical vertebra proximal scoliosis
Sagittal balance | KyphosisXX | NEED EXPLANATION
Vertebral orientations | RotationXX | NEED EXPLANATION
 

