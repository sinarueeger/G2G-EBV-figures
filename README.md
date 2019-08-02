# 

Creating all the figures and tables for the manuscript. 

This is basically 

- Figure 1 (illustration)
- Figure 2 + S1 + S2a + S2b + S3 + S4 + S5 (report/figure-tables.R)
- Table 1 (report/figure-tables.R)
- Figure S6 + S7 (src/results.R)
- Figure S8 (by hand locuszoomplot)

## Workflow

- store summary stats on Zenodo
- have a file for each figure and table prepared

## Usage

1. Install `holepunch` with `remotes::install_github("karthik/holepunch")`
2. Then run the following code:

```r
library(holepunch)
write_compendium_description(package = "Your compendium name", 
                             description = "Your compendium description")
# to write a description, with dependencies listed 
# It's good practice to now go fill in the placeholder text.

write_dockerfile(maintainer = "your_name") 
# To write a dockerfile. It will automatically pick the date of the last modified file, match it to 
# that version of R and add it here. You can override this by passing r_date to some arbitrary date
# (but one for which a R version exists).

generate_badge()
# This generates a badge for your readme.

# At this time 🙌 push the code to GitHub 🙌
# If you're new to Git/GitHub, you can click the Git tab on Rstudio, then click commit to see
# all changed files/folders, including the hidden .binder folder. Give this a commmit message and push

# And click on the badge or use the function below to get the binder built ahead of time.
build_binder()
# 🤞🚀

Now, run through analysis.R till you get to a plot
```

Does clicking the badge launch binder for you? If not, please [file an issue](https://github.com/karthik/binder-test/issues/new).
