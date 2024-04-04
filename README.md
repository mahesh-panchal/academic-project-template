# Academic Project Template

A template for reproducible academic projects. The idea of this template is to provide a structure 
and way of working that eases those wanting to work more reproducibly.

> [!IMPORTANT]  
> This is work in progress, as I slowly add material.

## Take it step by step

A large part of working reproducibly is building habits. Learning everything at once will also
be daunting and overwhelming and can hinder your adoption of reproducible practices as a result.
Building comfort with tools and practices over time and maintaing a reasonable level of challenge,
is a better recipe to succeed.

### 1. Decide on a folder structure

Before dumping all your files in a copy of this template, decide on a folder structure you want to
maintain. Keeping it as simple as possible will help maintain it over time.

This repository implements a suggestion:
```
/
|- analyses/  // Contains scripts that launch your workflows. Codify everything!
|- docs/      // Website, Slides, Reports, Articles, Thesis that use literate programming for reproducibility.
|- workflows/ // Workflows for large scale analyses, often executed on a HPC or other non-local system.
```

### Some literature

- [Folder structure, file names, and versioning](https://snd.se/en/manage-data/organise/folder-structure-filenames-versioning)
- [Easing Into Open Science: A Guide for Graduate Students and Their Advisors](https://online.ucpress.edu/collabra/article/7/1/18684/115927/Easing-Into-Open-Science-A-Guide-for-Graduate)
- [A Quick Guide to Organizing Computational Biology Projects](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424)
- [Ten Simple Rules for Reproducible Computational Research](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003285)
- [Ten simple rules for biologists learning to program](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005871)
- [Best Practices for Scientific Computing](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1001745)
- [Good enough practices in scientific computing](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005510)
- [Streamlining data-intensive biology with workflow systems](https://academic.oup.com/gigascience/article/10/1/giaa140/6092773)
