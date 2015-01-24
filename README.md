# Readme.md 

The tidy data can be read into R with the following code:
read.table("tidy_data_set.txt", header=TRUE)

## Description of run_analysis.R script

<< add description of script >>

There are some interesting threads on the course discussion board about wide vs. narrow formats for tidy data. I chose to use the wide format, aligning to these principles:

1) Each column represents a variable or measure or characteristic.
2) Each variable is in one column.
3) Each observation of the variable is in a different row.

## Special instructions for running run_analysis.R

run_analysis.R is written to work with the Windows file system. You'll need to modify the file paths in read.table to run on Mac/Linux systems.


## Description of tidy data

The codebook.md file contains the specific description of the tidy data file contents. 

The codebook still has the specific description of the tidy data file contents (and you mention that it exists and it's role in the ReadMe)
