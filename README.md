# LAPOP-dashboard
This repo contains the data for the Latin American Public Opinion Project. With this information, we aim to create web-based, interactive, self-guided analytics.

## Getting Started
These are the steps you should take to begin using this repo.

### Prerequisites
#### R Studio
You will need the current version of [RStudio](https://www.rstudio.com/products/rstudio/#Desktop) to run this code.

The code and text were written in an R Notebook. This is an R Markdown file (.rmd) that runs interactively. It does not require any additional installation, as it is a built-in function in R Studio. For an in-depth tutorial, visit this [R Notebook Guide](https://bookdown.org/yihui/rmarkdown/notebook.html). There are also [cheat sheets](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf) available for how to use R Markdown.

You will need to download all of the merged files that exist for each country individually from the [LAPOP Datasets](http://datasets.americasbarometer.org/database/index.php). Currently, you need to download the 2016/17 files separately, but in the future there may be a more recent merged file that includes these years.

In order to run this code, you will also need to install the following packages using `install.packages()`:
* [tidyverse](https://www.tidyverse.org/packages/)
* [haven](https://cran.r-project.org/web/packages/haven/haven.pdf)
* [labelled](https://cran.r-project.org/web/packages/labelled/vignettes/intro_labelled.html)
* [sjmisc](https://cran.r-project.org/web/packages/sjmisc/sjmisc.pdf)
* [assertr](https://cran.r-project.org/web/packages/assertr/vignettes/assertr.html)
* [janitor](https://cran.r-project.org/web/packages/janitor/janitor.pdf)
* [rlang](https://cran.r-project.org/web/packages/rlang/rlang.pdf)

Finally, you will need the excel files provided by the LAPOP organization that contains the current list of categories and questions to be visualized. The excel file should then be converted to .csv for use in RStudio.

You can find these files above. They are named as follows:
* "LAPOP categories unfactored.csv"
* "Lapop Categories factored.csv"
* "updated factor questions.csv"
* "updated unfactor questions.csv"

These files will need to be placed into the working directory of your project in RStudio.

#### Tableau Public
For the final visualizations, you will need to have [Tableau Public](https://public.tableau.com/en-us/s/) installed on your machine. There is a login that belongs to LAPOP, and this is the one you should use to save your visualizations to.

Tutorials to Tableau Public can be accessed [here](https://public.tableau.com/en-us/s/resources)

### Suggested Workflow
1. Reading in Data
    + Reads in the merged country and 2016/17 Stata files downloaded from the [LAPOP Datasets](http://datasets.americasbarometer.org/database/index.php)
    + Creates factored and unfactored versions of all datasets
 
2. Categories and Questions
    + Loads in the .csv files with appropriate categories and questions
  
3. Adding Wave Column
    + Creates a column that contains the correct wave for 2016/17 datasets.

4. Creating Unique ID
    + Makes a unique ID for merged country files that follows the unique ID of 2016/17 files.

5. Lengthening and Joining
    + Lengthens countries into tidy format
    + Joins the questions and category columns by column_name
    
6. Finding Common Questions
    + Narrows down the data to questions that are asked across all countries
    
7. Widening for Tableau Public
    + Widens the data to fit in the row limit for Tableau Public

8. Writing .csv
    + Writes .csv files to use in Tableau Public

# Team
* Carmen Canedo | Vanderbilt Data Science Institute Intern
* Lindsay Hardy | Vanderbilt Data Science Institute Intern
* Jesse Spencer-Smith | Chief Data Scientist at the Vanderbilt Data Scientist Institute
* Lindsey Fox | Senior IT Consultant for Research
