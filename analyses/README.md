# Analyses

This folder contains folders with scripts to run the project analyses. 
What constitutes an analysis will be up to you. You define the analysis 
entity and when it starts and stops, and when a new one should be begun.

It's useful to label folders starting with a lexicographic ordering, and 
a simple description. A lexicographic ordering can be using numbers starting 
at 01, or a date YYMMDD, or some alphabetical system.

Over time, as the number of analyses grows, it is useful to describe 
the relationship between analyses. A `History.md` file can be used to 
communicate how analyses relate to each other. 

For example:
- which folders run the same workflow but with different parameters.
- which folders run subsequent analyses to another folder.
- which folders result in useful data, were abandoned/unfinished, or the 
resulting data were of little use. 
- which folders use test data and develop workflows, and which folders 
run analyses on the full data sets.

```
analyses
  |
  | - History.md                (For longer projects, a history of which analysis lead to what)
  |
  | - 01_workflow_dev/          (Analysis folder used to develop workflow with test data)
  |     | - params.yml              (Parameter file for test data)
  |     | - nextflow.config         (Additional Nextflow configuration, such as custom process configuration)
  |     \ - run_nextflow.sh         (Shell script to call nextflow with correct parameters)
  |
  \ - 02_<short_desc>/          (Usually the workflow that runs all the data and where it should run)
        | - params.yml              (Parameter config for all data)
        | - nextflow.config
        \ - run_nextflow.sh
```

The folder contents described above gives an idea of what each analysis should contain (This example is specific 
to Nextflow, but can be generalised, for example using a parameterised notebook).

- `params.yml`: This is a file containing parameters passed to a Nextflow pipeline. Generally, it's a good idea
to record parameters used in a file, instead of using command-line options, or hard-coding parameters into scripts
as this makes your code reusable. 
- `nextflow.config`: This file contains other configuration information like profiles allowing you to run your 
workflow in different places, or customising resources to your execution platform. 
- `run_nextflow.sh`: In it's basic form, it's a script that calls nextflow with the parameters and configuration.
This can be extended to do other setup and cleanup work, such as initiating a run-time environment through conda,
loading container/package modules, or using `nextflow clean` to clean up working directories. 

