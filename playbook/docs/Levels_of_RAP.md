# Levels of RAP

For an introduction on what RAP is, and what benefits it can bring, please see our other guidance: “[How do I do RAP in health?](How_do_I_do_rap_in_health.md)”.

The purpose of this document is to outline a number of levels to work towards when developing and improving upon a Reproducible Analytical Pipeline (RAP). It outlines in a very specific way what RAP is, and this levelled approach gives analysts clear direction for how to develop their own skills and how to make their analytical pipelines more robust. This enhanced understanding can be beneficial to all involved. 

Note that we are not saying this exact framework should be used by all organisations. It is important to think about what your unique priorities and needs are as an organisation, and adapt the framework to fit. These levels are simply provided as a starting point for you to use. 

It is important to stress that RAP does not need to be an all or nothing exercise. Even implementing just some of the principles outlined here will bring about improvements to your processes and outputs. Trying to achieve all of these standards in one go may be too daunting a task and so incremental improvements are the suggested way to go.

It is also important to recognise that some of principles that form these standards may not always be possible. For example, where remote connections to databases are not permitted, this cannot be automated. In such cases, the aim should be to apply RAP to the other areas where principles can be applied. (Note though that it is preferred to have a direct connection to databases wherever possible, as any “black-box” processes conducted in extracting and preparing data for analysis might undermine some of the benefits of RAP.)


## Overview

| Things to focus on when getting started                    | Things to focus on for more enhanced efficiency and reproducibility | Things to focus on for even more enhancements around quality assurance and project management |
| ---------------------------------------------------------- | ------------------------------------------------------- | ----------------------------------- |
| [Have minimal manual steps for data extraction and analysis](#have-minimal-manual-steps-for-data-extraction-and-analysis) | Meet the previous standard                                | Meet the previous standard            |
| [Use open source analytical software](#use-open-source-analytical-software)                        | [Have minimal manual steps for the production of outputs](#have-minimal-manual-steps-for-the-production-of-outputs) | [Have unit testing](#have-unit-testing)                   |
| [Integrate quality assurance checks throughout the analysis](#integrate-quality-assurance-checks-throughout-the-analysis) | [Use functions as reusable blocks of code](#use-functions-as-reusable-blocks-of-code)                | [Have error handling for functions](#have-error-handling-for-functions)   |
| [Have well-commented code and documentation](#have-well-commented-code-and-documentation)                 | [Adhere to a common code style](#adhere-to-a-common-code-style)                           | [Include documentation for functions](#include-documentation-for-functions) |
| [Make code available to other analysts](#make-code-available-to-other-analysts)                     | [Have automated input data validation](#have-automated-input-data-validation)                    | [Use packaging](#use-packaging)                       |
| [Use version control software](#use-version-control-software)                               | -                                                      | [Log data and analysis checks](#log-data-and-analysis-checks)        |
| [Use peer review to ensure reproducibility](#use-peer-review-to-ensure-reproducibility)                  | -                                                      | [Implement continuous integration](#implement-continuous-integration)    |
| -                                                          | -                                                      | [Implement dependency management](#implement-dependency-management)     |


## Things to focus on when getting started

* have minimal manual steps (for example, minimal copy-paste, point-click, drag-drop operations) for data extraction where permissions allow (for example, using SQL code), and for the analysis steps used to produce numbers, tables and charts
* use open source analytical software (preferably R or Python)
* integrate quality assurance checks throughout the analysis, automated where appropriate, supplemented with semi-automated and manual checks
* have well-commented code and documentation embedded as part of the project, rather than being saved elsewhere
* make code open and available to other analysts (including external users where appropriate)
* use version control software such as Git and GitHub to create and maintain a recorded history of the project
* use peer review to ensure that the analysis is accurate and reproducible, and that the pipeline meets the rest of this standard


## Further details on these points:

### Have minimal manual steps for data extraction and analysis
Minimising the number of manual steps helps reduce the risk of human error. While automation is encouraged, this does not mean the entire pipeline needs to be run in one step. For example, trying to pull and shape data and produce outputs in the same line(s) of code might make it difficult for other analysts to follow what you are doing or reuse parts of your code for similar projects. Instead, your project might be separated out into several scripts denoting different stages of the pipeline. For example, you might have one script that pulls the data from the data store and condenses it down into one or more minimum tidy datasets: defined as the minimum amount of data needed to complete the publication. Those datasets can then be passed through an RMarkdown script to produce the report (or easily picked up for use in different projects!).

### Use open source analytical software
Open source tools such as R or Python are generally preferred over proprietary tools because they are better at reading a range of different data formats, support modularised code, and can be used to automate the creation outputs in a range of different formats (for example, markdown, HTML, Word, Excel and PowerPoint files - this will become important for meeting the other principle on automated outputs). They also reduce (or eliminate) the number of times where data needs to be moved from one programme into another (for example, from SPSS into Excel into Word). Open source, such as R and Python, is also better for transparency compared to other proprietary software where licenses are required to run the code. Those licenses can also be expensive, whereas there are no costs involved for most applications of R and Python. 

See this handy guide: [R for applied epidemiology and public health](https://epirhandbook.com/en/index.html).

### Integrate quality assurance checks throughout the analysis
Simply being reproducible does not mean that you are doing your analysis correctly. It is important to quality assure each stage of the process, not just the end product. Quality assurance should align with the principles outlined in the [Aqua Book](https://www.gov.uk/government/publications/the-aqua-book-guidance-on-producing-quality-analysis-for-government) and the [Code of Practice for Statistics](https://code.statisticsauthority.gov.uk/) for those who have adopted the code. 

Checks should be built in at various points throughout the code to flag anything unexpected for further (human) exploration. These might print warning messages into the console for example, or output more detailed markdown files flagging where potential issues might exist. Note that while many quality assurance checks can be automated, some human input will always be needed, such as for final proof readings and checking that automated text still matches the figures. 

Broader checks should also take place, such as checking that the analysis and outputs meet user needs and checking that any assumptions about the model or method are likely to be true. Code reviews are also a sensible thing to do.

To formalise your quality assurance processes and to keep an audit trail, it is a good idea to have defined roles (particularly the "assurer" and "analyst" roles), and keep detailed QA logs. 

### Have well-commented code and documentation
Having good quality documentation accompanying your code is important for reproducibility. The simplest form of documentation is code comments. These can be supplemented with additional documentation such as a “README” file. Standard Operating Procedures (SOPs), QA logs, assumptions logs are other good methods of documentation. 

Good documentation will help improve the reuse of code, either by other analysts using it for the first time or by the same analyst using it in the future. It should explain what the code does and how it can be used, including what options or parameters are available, examples of how to run it, and an explanation of any software or environment dependencies. It should be embedded as part of the project, rather than being saved elsewhere, so that it can be easily found. 

### Make code available to other analysts 
It is a good idea to make code available to others because this means that the pipeline can be reproduced should the usual analyst go on leave or leave the organisation. It should be stored in a place that is accessible to others (not on a local drive). Keeping code in a repository such as GitHub can also make it easier to find and provides a back up in case of accidental deletion (excluding anything sensitive such as datasets and database connection details).

Ideally, the code should be made publicly available for transparency, but [this may not always be appropriate](Exceptions_to_open_sharing_of_RAP.md). Please adhere to your organisational policy on this.

### Use version control software
Version control is important for documenting what changes have been made when, why, and by whom, as well as helping to ensure that people running your code know that they are using the right version. It can act as a safety net, allowing you to roll back to earlier versions of code in the event of an issue, or to review how an earlier report was produced.

[GitHub](https://github.com/) (or [GitLab](https://about.gitlab.com/)) can be used as a central repository to store your code and version history, allowing it to be easily accessed by others. Sharing code via GitHub can also help avoid duplication of work when other analysts are looking to perform similar tasks. GitHub also allows analysts to be open about areas they have identified for improvement via an issues log, also inviting ideas from others. Private repositories can be used for internal use only, or public repositories can be used to make your code more openly available. Please adhere to your organisational policy on open repositories if available.

It is important not to commit anything sensitive to version control repositories, such as datasets, secret keys and credentials. Datasets should be excluded to avoid disclosing any personal information. It is recommended that keys and credentials should be saved in a separate file that can still be used within the project, but which is excluded from the repository. Pre-commit hooks, such as those provided by the cross-government “[govcookiecutter](https://best-practice-and-impact.github.io/govcookiecutter/#govcookiecutter)” tool, or “.gitignore” exclusions can help mitigate this risk. Remember that even when sensitive information is included deep within the version history, these can be checked out and viewed.

While datasets are usually not committed to repositories, it is still important to ensure that some form of version control is applied to the source data, so that others know what version of the data was used for the analysis. If your project relies on snapshot CSV files, rather than connecting to a database directly, it is good idea to store those files in a read-only folder, to prevent them being modified or deleted - any changes like this could make it difficult to reproduce the same outputs in the future . For these files, it is important to ensure that they are saved prior to any data cleaning taking place, so that that data cleaning process can be documented within the production pipeline.

Even where direct connections to databases are made, it may be a good idea to save a copy of a tidy dataset (the minimum dataset needed to produce an output, rather than the full underlying dataset) at some point in the pipeline to keep a record of the data used, and so that it can also be reused in other projects. Please adhere to proper information governance procedures when doing this, however, avoiding saving copies of anything that might be considered sensitive.

### Use peer review to ensure reproducibility
The purpose of the peer review here is to ensure that the analysis is fully reproducible and that it does indeed appropriately meet the principles outlined in the framework above.

It can, for example, involve a peer testing whether they can successfully run your code, checking that documentation is clear and complete, and checking that version control has been appropriately implemented. 


## Things to focus on for even more enhancements around quality assurance and project management

* achieve all of the points above
* have minimal manual steps (for example, minimal copy-paste, point-click, drag-drop operations) for the production of spreadsheet workbooks and reports for publication
* use functions as reusable blocks of code
* adhere to a common best practice code style
* have automated input data validation  
  
## Further details on these points: 
  
### Have minimal manual steps for the production of outputs
Automating the production of outputs, such as reports, spreadsheets or dashboards, further reduces the risk of human error. There are packages available to help produce reports automatically, such as [RMarkdown](https://rmarkdown.rstudio.com/) and [Python-Markdown](https://pypi.org/project/Markdown/). Spreadsheet workbooks can similarly be produced using the [openxlsx package for R](https://cran.r-project.org/web/packages/openxlsx/index.html), for example. Producing outputs in these ways means that you know all elements of the output are in sync, as everything is produced from that single pipeline. With more manual approaches, forgetting to update the charts, for example, will mean that they are no longer in sync with what is presented in the text. A good test for how automated your pipeline is might be to think whether or not your outputs are deletable without worry. If you would not want to delete your outputs, because it would take time and energy to re-make them, then your end-to-end pipeline is not fully automated.

### Use functions as reusable blocks of code
Functions are particularly useful when you are repeating the same operations at multiple points in your code. Rather than writing out the same code each time you need to carry out an operation, you can create a function and call that each time instead. This lessens the risk of error because if you need to change that operation, you only need to change the function definition, not each place in the code where it is run (some of which may otherwise be missed). Functions also lend themselves nicely to sharing snippets of functional code with others.

### Adhere to a common code style
Working to a common code style makes it easier for other analysts to pick up your code as they will be able to interpret and understand it more quickly. We will be looking to develop a code style guide in the future. For R users, the [tidyverse style guide](https://style.tidyverse.org/) is the most commonly used style in the global community. "[PEP 8](https://peps.python.org/pep-0008/)" is an alternative for Python users. 

### Have automated input data validation
Validating your input data is important as the quality of your outputs will necessarily depend on the quality of the inputs. Remember: “garbage in, garbage out”. Validating those inputs in an automated way at the very start of the pipeline allows you to quickly identify and address any quality issues early. You might produce code to check, for example, for missing data, incorrect data types, extreme or outlier values, and whether there have been any unexpectedly large changes in the latest iteration of a longitudinal dataset. Other sense checks can also be performed. You could have your code produce a markdown document which flags any rows that may warrant further exploration - this may be particularly useful for any reports which are run on a regular basis.

Some useful packages for input data validation include:

* [assertr](https://docs.ropensci.org/assertr/) and [validate](https://cran.r-project.org/web/packages/validate/vignettes/cookbook.html) for R


## Things to focus on for even more enhancements around quality assurance and project management

* achieve all of the points covered under the bronze and silver standards
* have unit testing for functions
* have error handling for functions
* include documentation of functions (usually included as part of a package)
* use packaging
* log data and analysis checks
* implement continuous integration
* implement dependency management

## Further details on these points:  

### Have unit testing
Unit testing is where functions are tested with controlled inputs each time they are called, to check that expected outputs are returned. This can be a useful method to raise alarms if changes made to code elsewhere in the project, or some other environment change, adversely affects the function’s operation. The principle behind unit testing is that where the functionality of the smallest units of the code can be guaranteed, it is more likely that the overall project is running as expected. They also encourage analysts to focus more on quality assurance, and what the purpose of each piece of code is. Unit tests further act as another layer of documentation: it tells users what the intention behind a certain piece of code was and what the expected outputs are.

Some useful packages for unit testing include:

* [testthat](https://testthat.r-lib.org/) and [tinytest](https://github.com/markvanderloo/tinytest#readme) for R
* [pytest](https://docs.pytest.org/) for Python


### Have error handling for functions
[Error handling for functions](https://www.r-bloggers.com/2012/10/error-handling-in-r/) involves stating how the function should behave when it encounters something unexpected, such as a missing or incorrectly formatted parameter passed through the function call. Common actions might include stopping the code with an error message, or printing a warning message but allowing the code to continue.

### Include documentation for functions
It is sensible to provide documentation for your functions so that others know how to use them. Aspects of functions to document include its purpose, the parameters required in function calls along with any default values, and expected inputs and outputs. The preferred place to include this documentation would be within package help files and vignettes.

### Use packaging
A package more formally captures all the code and documentation required for a project or collection of functions in one place. It also allows for easier sharing of all the functions needed for a pipeline, or indeed the whole pipeline itself, as well as enhanced version control for the project (via package version numbers).

### Log data and analysis checks
Producing logs of data and analysis checks can help analysts, users and quality assurers to understand whether anything is going wrong with the pipeline, and to understand how and where to respond to any issues. These logs might include, for example, the outputs of any input data validation, unit tests, other checks, messages and warnings, as well as more manual checks (for example, via QA logs). The Office for National Statistics are planning to produce a chapter on this in the [Duck Book](https://best-practice-and-impact.github.io/qa-of-code-guidance/intro.html).

### Implement Continuous Integration
Continuous Integration (CI) describes the managed process of accepting and integrating changes made by individual analysts into a definitive main version of a project. For example, it includes the management of conflicts and the running of regular (automated) tests to ensure that no bugs have been introduced by recent changes. CI helps project leads to identify and resolve any conflicts and bugs early, and helps keep individual collaborators up to date with developments. [Pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) can be used in GitHub as part of this purpose, to require a sign-off step before any new code is accepted into the main pipeline. Branches can also be used to work on changes without the affecting the main pipeline until your are ready, for example to build in a new feature or when fixing a bug.

### Implement dependency management
Dependency management is important as your code is ultimately dependent on the specific state of the software used at the time the analysis is run. If the environment differs for another analyst, or for the same analyst in the future (for example, following software and package updates), the outputs may differ. A simple illustration of this kind of issue is provided by the Turing Way Community: A basic division of 1 by 5 can either return 0 or 0.2, depending on which version of Python is being used (Python 2 defaults to integer division; Python 3 does not). To combat risks such as these, details of the environment can be stored, such as via the [renv package](https://cran.r-project.org/web/packages/renv/index.html) for R or via a [Docker container image](https://www.docker.com/). These tools save a record of the environment in which the analysis was originally performed, allowing others to restore that same environment.

