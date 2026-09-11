# A Hybrid Random Forest - Neural Network Approach to Identifying Genetic Signatures of Pediatric Crohn's Disease from RNA-Sequencing Data

   ## Overview

This project applied machine learning to RNA-sequencing data from 210 pediatric individuals diagnosed with Crohn’s disease (CD) and a control group of 35 individuals without inflammatory bowel disease (IBD). All individuals with pediatric CD were treatment-naive. This data was obtained from the RISK study, and the original source is linked at the bottom. The goal was to identify genes that were most informative for distinguishing disease from healthy states and to investigate the biological pathways associated with pediatric CD.

A hybrid machine-learning approach was implemented, in which a **Random Forest (RF) classifier** was first used for feature selection prior to training a **neural network (NN)**. The RF model, built with 1,000 decision trees, identified an optimal set of **80 genes** that produced the highest **classification accuracy, ~95%,** during NN training. After testing several parameter configurations and architectures, the final NN consisted of a dense layer of 32 neurons and a dropout layer, with L2 regularization applied to shrink weights and further improve accuracy.

The resulting model achieved an **AUROC of 0.986**. The **F1 scores were 0.98 and 0.83** for positive and negative classifications, respectively. It is also noteable that **recall for the CD class was 1.00**. That is, no CD patient was misclassified as a non-CD control, which is a clinically meaningful result given the cost of missing true disease cases. It is also worth noting that the dataset is imbalanced, with a majority-class baseline accuracy of 0.85. The model's 0.95 accuracy therefore represents a modest but meaningful 0.10 margin over that baseline. Model figures and metrics are attached in another file.  

Gradient-based feature attribution identified the genes that were most influential in the neural network's predictions. The top 15 most influential, based on this metric, are provided below:

<img width="346" height="440" alt="top 15 genes" src="https://github.com/user-attachments/assets/9b5e172b-8989-421e-9c61-9af2c919a00f" />


Metascape, Reactome, and Enrichr were subsequently used for **pathway analysis of all 80 genes** used in NN prediction. This revealed strong enrichment in immune-related processes, particularly those associated with **inflammatory response, immune cell chemotaxis, and cytokine signaling**, along with **extracellular matrix remodeling and profibrotic mediator pathways**. This is consistent with the chronic mucosal inflammation and tissue remodeling characteristic of Crohn's disease. The figures produced from pathway analyses are attached in another file. 

Overall, the findings demonstrate the potential of machine-learning approaches to identify biologically relevant molecular signatures from transcriptomic data. More investigation should be done into other possible model architectures, and comparisons should be made to other ML models such as SVMs, KNNs, and logistic regression. 

Original Dataset Source: https://www.ebi.ac.uk/gxa/experiments/E-GEOD-93624/Results?specific=true&geneQuery=%255B%255D&filterFactors=%257B%257D&cutoff=%257B%2522foldChange%2522%253A1%252C%2522pValue%2522%253A0.05%257D&regulation=%2522UP_DOWN%2522

## How to Run

1. Download the provided source .zip file
2. Extract the contents of the .zip file
3. Download the provided .ipynb Jupyter Notebook
4. Open the notebook in JupyterLab or another compatible environment
5. Run the notebook cells in order
