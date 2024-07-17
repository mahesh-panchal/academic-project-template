# README

When you can not fetch data programatically through your workflows or from public archives,
it's a good idea to have a common place to store it.

> [!CAUTION]
> Data stored in these subfolders must not be tracked with Git (Use `git status`
> to verify before running `git add`). The only parts that are intended to be
> tracked are the top-level folder structure, README files, and data provenance scripts.

## A suggested structure

This is a simple folder structure suggestion, however these labels can mean different things
to different people, so choose labels that you deem appropriate for the purpose.

```
/data
    | - deliveries    (data deliveries in their unmodified form and made read-only)
    | - raw-data      (subfolders named after library-type, symlinked to files in deliveries)
    | - outputs       (workflow/script outputs from exploratory phase)
    \ - finalised     (symlinked folders to `outputs` marking analysis phase end-points)
```

### Deliveries

It's valuable to have a copy of the data in the form you received it. Make it read-only 
(`chmod -R uga-w <delivery_folder>`) so no accidental corruptions can occur, and make
a back-up in an alternate location too.

Codify downloads from any public archives, and use a password or secrets manager for gated
access points.

```bash
#! /usr/bin/env bash

curl -O ftps://path/to/public/archive/file.fasta
```

### Raw data

Data received from outside providers can sometimes be in deeply nested folder structures,
making using them unwieldy, or contain lots of extra data for the project. Use this 
raw-data folder to make a more organised view of the data for working, by symlinking
files in appropriate folders.

### Outputs

Store your analysis results in this folder that are relevant to evaluation.
Use a folder in a `nobackup` directory to isolate intermediate files from a run.

### Finalised

These are symlinked folders linking to outputs folders of results that should not change 
further, for example for publishing, or public archiving.
