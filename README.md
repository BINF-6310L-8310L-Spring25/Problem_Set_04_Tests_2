# Problem_Set_4_ANOVA

This week we are going to use another NASA dataset this week!

#### Correlated Gene and Protein Expression in heads from Drosophila reared in microgravity

https://osdr.nasa.gov/bio/repo/data/studies/OSD-207


_Description of the study_
Fly lines used in this study were Canton S laboratory wildtype lines (Bloomington Stock Center), a K+ channel mutant seizure (seizurets1, a gift from Dr. Barry Ganetsky), a K+ channel mutant KCNQ180 and genetic control KCNQ97 (precise and imprecise p-element excisions respectively, Ocorr et. al., PNAS 2007). Flies launched to the International Space Station (ISS) as well as ground controls were housed in polystyrene vials (75 x24 mm) with 10 ml of standard cornmeal-based fly food containing double the usual amount of 10% tegasept and cellulose acetate plugs. Approximately 24 hours prior to launch, 15 vials were each loaded with 8 female and 5 male adult virgin flies; loaded vials were placed in a Plexiglas tray and inserted into a vented fly box (VFB), a modified version of a Nanoracks box. The VFB was placed into a canvas case for loading into the Dragon capsule. Launch occurred at 19:25 UTC on 04/18/14. Flies were kept in the VFB throughout the 30 day mission and were stored aboard the Dragon capsule that was docked and sharing atmosphere with the ISS. Ambiant temperature (~21˚C) for rearing. The Dragon capsule unberthed at 13:26 UTC (Co-ordinated Universal Time) on 05/18/14 and re-entry occurred the same day at 19:05 UTC. After retrieval of the Dragon Capsule off the coast of Mexico the VFB was offloaded at Long Beach Port, CA and transported by car to La Jolla, CA in a climate controlled vehicle. Asynchronous ground control flies were prepared and reared under identical conditions in ground-based incubators with temperature and humidity controlled to levels recorded on the ISS.

There are two files:
Expression data with gene info: GLDS-207_rna_seq_ERCCnorm_differential_expression.csv 
Sample Data: OSD-207-samples.csv

### Step 1

Import the two files and create a data frame in which each row is an individual sample (fly), and the columns are the samples (gene expression data) and their sample characteristics (including space flight and Genotype)



Your dataset should look something like this (click to enlarge)
![image](https://user-images.githubusercontent.com/47755288/216450492-9c483482-cb07-4555-ac29-c824086c65fb.png)

# Lab Question 1 (1 point)

How many flies have the **genotype "CS"** and **gene expression for the gene "FBgn0000015" greater than 1**. 

### Step 2 (5 points)

There are 13,885 genes! We want to narrow our focus to genes that have a difference between space flight and ground control. So let's identify all of the genes that have a difference in mean expression between space flight and ground control (regardless of genotype)

1 - Multiple Tests Correction. Let's use the Bonferroni adjustment for our p-value. What is the adjusted p-value for 13,885 tests?

2 - Create a loop that will generate a data frame containing just the space flight and gene expression information 

3 - Within this loop, conduct a One Way Anova to test for a difference in means 

4 - Save the positions or gene names for the One Way Anova tests with a Pr(>F) less than our adjusted p-value 

5 - Report the total number of genes with a statistically significant difference in mean gene expression


### 3 Investigate the gene FBgn0038749 (6 points)

You should have gotten the gene FBgn0038749 as one with a statistically significant difference in means for space flight and ground control 

Let's check our assumptions for this dataset to make sure we should continue with our analysis! 

1 - Conduct the Bartlett test of homogeneity of variances. Does our dataset violate the assumption of homogeneity?

2 - Conduct the Shapiro-Wilks normality test on the residuals of the gene expression values. Does our dataset violate the assumption of normality?

3 - Create a boxplot of the expression of FBgn0038749 between space flight and ground control 

4 - You are curious if genotype has influenced your results. Conduct 2 Two-Way ANOVAs using both spaceflight/control and genotype. In one do not predict interaction between the variables. In the second allow for interaction between the variables. 

5 - Generate and use the AIC table to report the best model. Is there an interaction between space flight and genotype?

6 - What is the gene name of FBgn0038749




### 4 Investigate the gene FBgn0033687 (6 points)

Let's look at another gene FBgn0033687. Repeat the above analyses. 


1 - Conduct the Bartlett test of homogeneity of variances. Does our dataset violate the assumption of homogeneity?

2 - Conduct the Shapiro-Wilks normality test on the residuals of the gene expression values. Does our dataset violate the assumption of normality?

3 - Create a boxplot of the expression of FBgn0038749 between space flight and ground control 

4 - You are curious if genotype has influenced your results. Conduct 2 Two-Way ANOVAs using both spaceflight/control and genotype. In one do not predict interaction between the variables. In the second allow for interaction between the variables. 

5 - Generate and use the AIC table to report the best model. Is there an interaction between space flight and genotype?

6 - What is the gene name of FBgn0033687

### Step 5 - knit and upload your document (1 point)
