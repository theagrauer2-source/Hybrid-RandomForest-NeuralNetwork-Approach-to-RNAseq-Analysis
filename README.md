# Project 1: A Hybrid Machine Learning Approach to Identifying Genetic Signatures of Pediatric Crohn's Disease from RNA-Sequencing Data
 ## Overview

This project applied machine learning to RNA-sequencing data from pediatric individuals diagnosed with Crohn’s disease (CD) and a control group without inflammatory bowel disease (IBD). The goal was to identify genes that were most informative for distinguishing disease from healthy states and to investigate the biological pathways associated with pediatric CD.

A hybrid machine-learning approach was implemented in which a **Random Forest (RF) classifier** was used for feature selection prior to training a **neural network (NN)**. The RF model identified an optimal set of **275 genes** that produced the highest classification accuracy during NN training.

Pathway analysis of the selected genes revealed strong enrichment in **immune-related processes**, particularly those associated with granulocyte function. The top upstream regulators were also highly associated with **cytokine signaling and immune-response regulation**, highlighting the importance of these processes in the molecular landscape of pediatric CD.

The neural network trained on the 275 selected genes achieved **97% classification accuracy** between healthy and disease states. Notably, when the NN was trained using only the single highest-ranked gene identified by the RF classifier, it still achieved **88% accuracy**. This gene was **PELATON (LINC01272)**, a long non-coding RNA previously reported to be upregulated in pediatric CD.

Overall, the findings demonstrate the potential of machine-learning approaches to identify biologically relevant molecular signatures from transcriptomic data. The strong performance of LINC01272 as a single feature also highlights the potential importance of **long non-coding RNAs** in understanding pediatric Crohn’s disease and identifying potential therapeutic targets.
