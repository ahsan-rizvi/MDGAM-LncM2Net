# MDGAM-LncM2Net
Multi-Layer Deep Graph Attention Model for lncRNA–miRNA–mRNA Regulatory Network in Human Cancers

## Project Overview
MDGAM-LncM2Net is a cutting-edge computational framework designed to construct and analyze cancer-specific lncRNA–miRNA–mRNA (LncM2) competing endogenous RNA (ceRNA) networks using multi-omic transcriptomic data and experimentally validated RNA interactions. By integrating graph attention networks with bidirectional LSTMs, the model captures both the complex regulatory topology and temporal gene expression patterns to identify key driver lncRNAs and prognostic gene modules across multiple cancer types. This approach improves interpretability and predictive accuracy for patient survival outcomes, providing a powerful tool for precision oncology research and clinical translation.

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
├── data/
│   ├── Data.Rdata           # A file containing cancer data
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
2. Run

To run the model, run the R_Script.R and main.py script. You can customize training parameters such as the number of epochs, learning rate, and other hyperparameters by passing arguments to the script.

```bash
python3 Code/main.py
```
```bash
source(Code/R_Script.R)
```
## Publication
Shivani Saxena, Ahsan Z Rizvi, , _Under review_

## Contact
Dr Ahsan Z Rizvi, ahsan.rizvi@iar.ac.in
