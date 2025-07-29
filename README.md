# MDGAM-LncM2Net
An Interpretable Deep Graph Model for Cancer-Specific ceRNA Network Analysis

## Project Overview
MDGAM-LncM2Net is an advanced computational framework for constructing and analyzing cancer-specific lncRNA–miRNA–mRNA (LncM2) competing endogenous RNA (ceRNA) networks. Leveraging multi-omic transcriptomic profiles and experimentally validated RNA interactions, the model integrates graph attention networks (GATs) with bidirectional long short-term memory (BiLSTM) networks. This dual architecture captures both the intricate regulatory topology of ceRNA interactions and the temporal dynamics of gene expression. By doing so, MDGAM-LncM2Net enables the identification of key regulatory lncRNAs and prognostic gene modules across diverse cancer types. The framework significantly enhances the interpretability and predictive accuracy of survival outcome models, offering a powerful tool for precision oncology and clinical translational research.

## Data Description
The framework requires:

* Multi-omic transcriptomic expression profiles: Matched lncRNA, miRNA, and mRNA expression data from cancer patient samples.

* Experimentally validated RNA interaction data: High-confidence miRNA-target interaction datasets including miRNA-lncRNA and miRNA-mRNA bindings.

* Survival clinical data: Patient survival times and event status for prognosis analysis.

These data are preprocessed and filtered to focus on cancer-specific dysregulated genes before integration into the model pipeline. 

## Code Description
The repository contains implementations of:
* Data preprocessing and differential expression analysis
* Hypergeometric and Spearman correlation tests for candidate ceRNA pair identification
* Fast Causal Inference (FCI) algorithm to infer directed regulatory relationships
* Graph Attention Network (GAT) models to learn network topology
* Bidirectional LSTM models to capture temporal gene expression dynamics
* Survival analysis modules to evaluate prognostic significance of identified modules
* Visualization tools for ceRNA network and module exploration

The code is modular and extensible for application across different cancer types or other transcriptomic datasets.

## File Structure
The file structure of the repository is as follows:
```.
├── Data/
│   ├── data.Rdata           # A file containing cancer data
├── code/
│   ├── Funnction.R          # Data integration and survival analysis function
│   ├── R_Script.R           # MDGAM-LncM2Net pipeline to evaluate lncRNA-miRNA-mRNA regulatory network
│   ├── utils.py             # Metric and utility functions
│   ├── main.py              # Python main script
│   └── model.py             # Custom layers for the model
├── README.md                # Project overview and instructions
└── requirements.txt         # Python dependencies
```

## Installation
1. Prerequisites
Make sure you have following libraries installed.
* R (version ≥ 4.0) with required packages.

* Python (version ≥ 3.7) with deep learning libraries.

* Additional dependencies specified in requirements.txt

2. Setup

Clone this repository:
```bash
git clone https://github.com/ahsan-rizvi/MDGAM-LncM2Net.git
cd MDGAM-LncM2Net
```
Install R packages:

```bash
install.packages(c("survival", "survcomp", "igraph", ...))
```

Install Python dependencies:
```bash
pip3 install -r requirements.txt
```
3. Run

To run the model, run the R_Script.R and main.py script. You can customize training parameters such as the number of epochs, learning rate, and other hyperparameters by passing arguments to the script.

```bash
python3 Code/main.py
```
```bash
source(Code/R_Script.R)
```
## Publication
Shivani Saxena, Ahsan Z Rizvi, Multi-Layer Deep Graph Attention Model for
lncRNA–miRNA–mRNA Regulatory Network in Human
Cancers, _Under review_

## Contact
Dr Ahsan Z Rizvi, ahsan.rizvi@iar.ac.in
