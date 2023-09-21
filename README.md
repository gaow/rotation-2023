# Fall 2023 first year MS research assistant rotation

## Overview

The overall research theme of our lab can be found in the lab wiki at: https://wanggroup.org/. 
As of now (September 15, 2023) most of the project specific contents are out-dated and still need to be updated.
Instead, here I will outline some of the research topics relevant to your future projects in the orientation tasks below. 

Before you decide if you would like to start working with us, please read the [lab "rules"](https://wanggroup.org/orientation/index.html#lab-rules), particularly a section for "Master students".
Please think carefully through about the committement to our lab and evaluate if it fits your future plans.
You can also talk to my current Biostatistics master students (Anjing Liu, Haochen Sun and Zining Qi) about their experiences working in the lab.
If you find everything is reasonable to you, please book meeting with me to discuss your rotation project.

In the next month, you will pick a rotation project and push it forward as much as you can.
The projects are designed for somewhat savvy students to complete within a month, so I don't expect everyone to complete all the tasks.
What's perhaps more important is to demonstrate your motivation, hardwork, communication and problem solving skills during the month of work.
In particular, **your ability to work well with the senior trainee(s) who will be supervising your work alongside with myself**. 
This aspect is of crucial importance in our lab. We need trainees to get along well and stimulate each other to be productive.
Even if you don't end up working in my lab, there are at 5 other labs in my department who would take referrals from me for those who do well in my rotation projects.
It is therefore in your own interest to complete the rotation project as much as possible to earn an opportunity working at our department.

Below, I outline 4 projects for you to choose from. Project 2 and 3 are the same material at the rotation phase so technically you are choosing from 3 rotation projects.
Please take a look at them before we discuss. However, I would suggest to not pick it yet until after our interview --- I would like to hear and know you better, and recommend a project for you, based on my past experiences interacting with first year students of diverse backgrounds. 
These rotation projects might not be as daunting as they seem to --- current master students in my lab has gone through the same in their first year, and are willing to help you. 

After our interview please send me your Slack account so I'll invite you to my lab slack workspace. Once you join my workspace, I will create channel for you to work with my team on your rotation projects. You can ask any questions in the channel. We will respond and interact with you from there.

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
However, for our method to become reliable analytical tool for the community to make important discovery from their data, it is crucial to ensure, to the best of our knowledge, that our implementation is correct, is execellent in its engineering quality, and is very much user-friendly (with target users being mostly practitioners who have strong domain knowledge but may not be savvy at statistical modeling and software engineering).
To achieve this goal:

1. The implementation must be well-tested using a ["unit testing"](https://en.wikipedia.org/wiki/Unit_testing) framework implemented in R.
2. The R scripts must be packaged into an R library, with good documentation for all the functions that we expect users to interact with (those R functions that we `export` to the namespace of the R library).
3. The R package should be well-engineered: improvements at this point includes refactoring the main interface, adding plot functions and improve & optimize CPU and memory usage via line profiling.

These 3 tasks are somewhat independent to each other --- if you pick this project please discuss with me what might be a good starting point for you. In the ideal case, you complete all of them at the end of the rotation.
To get started, please follow instructions in [this notebook](https://github.com/gaow/rotation-2023/blob/main/data/colocboost/colocboost_rotation_instructions.ipynb). 

### Outcome

For those who does execellent job in this task, you will be credited as a maintainer of this R library that we will publish on https://cran.r-project.org/. Depending on how helpful your work is, evaluated by myself and two other trainees in my lab who lead the project, you may also be listed as a co-author of our manuscript which we expect to publish early next year.

### Next steps until April, 2024

Students who successfully completed this assignment may be involved in a similar, but more challenging task of coding and improving another new statistical method we are developing, to integrate a vast range of functional genomic features to improve the accuracy of gene mapping and colocalization analysis. For example, it may even involve GPU computing in R which we have never explored ourselves. We will also conceive a project spinning from this theme that you could take lead on for summer 2024.

In this process you will be working closely with our postdocs Dr. Xuewei Cao and Dr. Ru Feng, as well as our 2nd year master student Haochen Sun.

### Next steps for summer 2024

One possible project that you can lead independently might be to extend a statistical fine-mapping method with a more informed prior on genetic effect size, compare the approach with the original in simulation settings, and apply to fine-mapping for Alzheimer's disease.

## Project 2: Adopting and applying a new statistical method to discover cis-regulatory network from quantitative trait loci analysis

### Aim

This project will allow you to demonstrate your **bioinformatics data analysis skills**, and later your data science skills to generate new knowledge from your own data analysis.

### Details

Imagine a simple task to identify DNA variations that might impact the RNA expression of its near by gene --- say you have 1,000 brain tissue samples, for each sample you measure the expression level of a gene, say *APOE*, which is a real number $y > 0$. You also measure the sequence the DNA near this gene, represented as a vector of integers $X$, taking values from {0,1,2} representing the copies of minor alleles of a genetic loci. To evaluate if a change in the DNA sequence has an impact on the gene expression level, one popular method is to perform a linear regression between $y$ and each variant in $X$ over all the 1,000 samples you have. This process is formally known as "eQTL" mapping (because we are analyzing gene **e**xpression **q**uantitative **t**rait **l**oci). To get a feeling of this process in practice, I suggest you watch [this video on YouTube](https://www.youtube.com/watch?v=24U8lyqu65A).

In our lab, we have resource to perform extensive QTL analysis (not just eQTL but many other type of QTL) for each of the genes in the genome with its nearby DNA variants. We would like to specifically focus on those variant that impact **multiple nearby genes**, to *prioritize* them as target of interest for follow-up studies because they potentially have a greater impact to biological functions than those that regulate just one gene at a time. To achieve this, we need to:

1. Perform conventional cis-QTL discovery along the line of the procedures outlined in the YouTube video.
2. Perform cis-network discovery using a new method we recently developed in a context different from cis-network discovery.

For the rotation project you are only expected to complete task 1, which is essentially to apply the steps outlined in the YouTube video to a small example data-set that we have prepared for you, using the software pipeline we have developed in the lab. By performing this analysis you will be well-trained to conduct QTL discoveries from real-world data.
To get started, please follow instructions in the "xQTL association analysis" of [this notebook](https://github.com/cumc/xqtl-pipeline/blob/main/code/xqtl_protocol_demo.ipynb).

### Outcome

For those who does execellent job in this task, you will be asked to perform additional similar analysis which will contribute to a large consortium project, and you will be listed a co-author on our manuscript which we expect to publish next year.

### Next steps until April, 2024

Students who successfully completed this assignment will continue to learn and contribute to the consortium project discover various types of QTL beyond eQTL. 

In this process you will be working closely with our 2nd year master students Zining Qi and Anjing Liu, as well as our postdoc Dr. Ru Feng.

### Next steps for summer 2024

Students will lead on the cis-network discovery using resources built from the QTL discovery above, adopting and applying our new statistical method called mvSuSiE, and furnish the results into a manuscript to be published in late 2024 or early 2025. 

## Project 3: Context specific molecular QTL discovery to elucidate Alzheimer's disease etiology

### Aim

Same as Project 2.

### Details

The assignment for rotation is exactly the same as Project 2 --- please follow the detailed instructions there. The difference is the problem we address with this project: traditional QTL discovery typically focus on all the samples available to an investigator, assuming the effects of QTL in these samples are the same. However, it is also well known that QTL can act in context specific fashion. For example tissue, cell type, age, sex, and biomarkers of a person can have impact in the way the DNA variant regulates molecular phenotypes. Of particular interest to our lab is curating and examining QTL in the brain and blood to investigate their influence on the blood-brain barrier and the regulatory processes associated with neurodegenerative disorders.

Analysis outlined in Project 2 can be similarly applied for context specific QTL. To get started, please read Project 2 Details and Outcome and Next steps until April, 2024.

### Next steps for summer 2024

Student will lead on a manuscript exploring context specific QTL and context specific cis-QTL network relevant to Alzheimer's disease.

## Project 4: Simulation study for a new method to discover trans-regulatory network from quantitative trait loci analysis

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

In this process you will be working closely with our postdoc Dr. Xuewei Cao and 5th-year undergraduate student intern Yifei Wang. You will also interact with Dr. Kushal Dey and his trainee at MSKCC.
