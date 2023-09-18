# Fall 2023 first year MS research assistant rotation

## Overview

The overall research theme of our lab can be found in the lab wiki at: https://wanggroup.org/. 
As of now (September 15, 2023) some project specific contents are a out-dated. 
I will outline some of the research topics relevant to your projects in the orientation tasks below. 

Before you decide if you would like to start working with us, please read the [lab "rules"](https://wanggroup.org/orientation/index.html#lab-rules), particularly a section for "Master students".
If you find these are acceptable to you, please reach out to me to start your rotation project.

In the next month, you will pick from one of the 3 projects and push them forward as much as you can.
The projects are designed for somewhat savvy students to complete within a month, so I don't expect everyone to complete all the tasks.
What's perhaps more important is to demonstrate your motivation, hardwork, communication and problem solving skills during the month of work.
In particular, **your ability to work well with the senior trainee(s) who will be supervising your work alongside with myself**. 
This aspect is of crucial importance in our lab. We need trainees to get along well and stimulate each other to be productive.

Below, I outline 3 projects for you to choose from. 
Please browse them, but I would suggest to not pick it yet before our interview --- I would like to hear and know you better, and recommend a project for you, based on my past experiences interacting with first year students working on projects from my lab.

## Project 1: Building software package for a new "colocalization analysis" method we have recently developed

### Aim

This project will allow you to demonstrate your **software programming and scientific computing skills**.

### Details

We are interested in "gene-mapping", ie, to identify DNA variation that may lead to a series of events spanning the Central Dogma of Biology.
This include but not limited to mapping where in the genome the DNA would lead to changes in the so-called "multi-omics" features, such as epigenomic marks, RNA expression, post-transcriptional processes, protein expression, metabolomics products, and complex disease risk such as Alzheimer's disease. 
Identifying such variations with potential evidence to "regulate" *multiple* such molecular features and complex traits is called "colocalization analysis". 
This is a challenging task because many DNA variants are correlated to the truly causal variant of various outcomes (you can roughly understand this as a variable selection problem of regressors in linear regression setting), 
and they may have an impact on only a subset of possible outcomes amoung many outcomes evaluated.

We have developed a new colocalization analysis method which showed great potential advantages over existing methods to address these two challenges.
Currently, we have implemented a prototype in the R programming language sufficient for in-house use to perform simulation studies and data analysis.
However, for our method to become reliable analytical tool for the community to make important discovery from their data, it is crucial to ensure that our implementation is correct, is execellent in the quality of engineering to the best of our knowledge, and is very much user-friendly because our target users are mostly practitioners with strong domain knowledge but may not be savvy at statistical modeling and software engineering.
To achieve this goal:

1. The implementation must be well-tested using a ["unit testing"](https://en.wikipedia.org/wiki/Unit_testing) framework implemented in R.
2. The R scripts must be packaged into an R library, with good documentation for all the functions that we expect users to interact with (those R functions that we `export` to the namespace of the R library).
3. The R package should be well-engineered: improvements at this point includes refactoring the main interface, adding plot functions and improve & optimize CPU and memory usage via line profiling.

These 3 tasks are somewhat independent to each other --- if you pick this project please discuss with me what might be a good starting point for you. In the ideal case, you complete all of them at the end of the rotation.
To get started, please follow instructions in [this notebook](https://github.com/gaow/rotation-2023/blob/main/data/colocboost/colocboost_rotation_instructions.ipynb). 

### Outcome

For those who does execellent job in this task, you will be credited as a maintainer of this R library that we will publish on https://cran.r-project.org/. You may also be listed as a co-author of our manuscript which we expect to publish early next year.

### Next steps until April, 2024

Students who successfully completed this assignment may be involved in a similar, but more challenging task of coding and improving another new statistical method we are developing, to integrate a vast range of functional genomic features to improve the accuracy of gene mapping and colocalization analysis.

## Project 2: Adopting and applying a new statistical method to discover cis-regulatory network from quantitative trait loci analysis

### Aim

This project will allow you to demonstrate your **bioinformatics data analysis skills**, and later your data science skills to generate new knowledge from your own data analysis.

## Project 3: Simulation study for a new method to discover trans-regulatory network from quantitative trait loci analysis

### Aim

This project will allow you to demonstrate your **understanding of statistical models and ability to implement and evaluate them**. 

### Details

It is well-known that DNA variations inside of or nearby a gene are likely to have a strong impact on the target gene (for example, *cis* analysis in Project 2). However, it is also known that many DNA variations may have an impact on genes far away from where they are. This is called the *trans* effects of genetic variants. This is a challenging task because there are many potential targets of *trans* variants across the entire genome (compared to *cis* analysis where only near by genes are examined), and the *trans* effects are often much weaker than *cis* effects. However, successful *trans* analysis can lead to many genes discovered that are co-regulated by certain genetic loci, and it is of great interest to unveil such shared molecular mechanisms of gene regulation.

Using the vast multi-omics data we have in the lab, we would like to uncover genetic regulation of trans-networks relevant to neurodegenerative disorders, particularly Alzheimer's disease. Existing analysis methods only analyze one "modality" of multi-omics data at a time, eg, they only analyze RNA expression. We have proposed extensions of existing methods to analyze network involving many modalities of molecular traits.
To achieve this goal, we need to:

1. Implement a comprehensive simulation study to evaluate our new method, as well as some competitor methods.
2. Apply a prototype of our new method to simulated data, as well as applying at least one competitor method.
3. Develop performance metric to benchmark the performance of our method as well as other methods.

These 3 tasks is sequential: you must carry them out in the order listed above. 
To get started, please follow instructions in [this notebook](). 

### Outcome

For those who does execellent job in this task, you will be included as a co-author of our manuscript which we expect to publish later next year.

### Next steps until April, 2024

Students who successfully completed this assignment will continue to be involved in applying the new method to analyze our vast multi-omics data, to learn about a series of related advanced statistical analysis on omics data, and to conceive a project spinning from this theme that they could lead on for summer 2024.

