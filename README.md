# A<Sup>2</Sup>SIGN: Agnostic Algorithms for Signatures

## PURPOSE

Molecular signatures are critical for inferring the proportions of cell types from bulk transcriptomics data. However, the identification of these signatures is based on a methodology that relies on prior biological knowledge of the cell types being studied. When working with less known biological material, a data-driven approach is required to uncover the underlying classes and generate ad hoc signatures from healthy or pathogenic tissue.
We present a new approach, A<Sup>2</Sup>SIGN: Agnostic Algorithms for Signatures, based on a non-negative tensor factorization strategy that allows us to identify cell type-specific molecular signatures, greatly reduce collinearities, and also account for interindividual variability. We propose a global framework that can be applied to uncover molecular signatures for cell type deconvolution in arbitrary tissues using bulk transcriptome data.
All steps of our analysis are implemented in annotated Python notebooks. To perform non-negative tensor factorization, please use the [NMTF](https://github.com/paulfogel/NMTF) package, which you can download with `pip install nmtf`.

## AUTHORS
Galina Boldina<sup>1</sup>, Paul Fogel<sup>l234</sup>, Corinne Rocher<sup>1</sup>, Charles Bettembourg<sup>1</sup>, George Luta<sup>5</sup>, Franck Augé<sup>1</sup>

<sup>1</sup> Sanofi, R&D Translational Sciences France, Bioinformatics, Sanofi, 91385 Chilly-Mazarin Cedex, France;  
<sup>2</sup> Consultant, 132 rue d'Assas, 75006, Paris;  
<sup>3</sup> Advestis, 69 boulevard Haussmann, 75008, Paris, France;  
<sup>4</sup> Quinten, 8 rue Vernier, 75017, Paris, France;  
<sup>5</sup> Department of Biostatistics, Bioinformatics and Biomathematics, Georgetown University, Washington, DC, 20057, USA 


## INSTALLATION

__Dependencies__: A number of libraries are required to be installed with pip: pandas, numpy, sklearn, adjustText, scipy, matplotlib, seaborn, nmtf, IPython and tqdm.
The A<Sup>2</Sup>SIGN method is implemented in two Jupyter notebooks (see description below), which are available on GitHub and run on Python v3.6 and higher.

## USAGE
### EXAMPLE NOTEBOOKS

Two example Jupyter notebooks are provided:
 - NTF_ABIS.ipynb - example of signature definition from FACS filtrates (ABIS dataset).
 - deconvolution.ipynb - example of deconvolution on a bulk dataset using a reference signature previously obtained from FACS filtrates.
All data required for the examples are located in the "data" folder.

### DEFINE REFERENCE MOLECULAR SIGNATURES
#### Input files
1. Expression data from purified/sorted cell types.
The gene expression matrix of your samples must be in an Excel format. The gene names must be gene symbols and there must be no duplicates, the genes must be in rows and the samples in columns. 
2. True proportions from FACS data for samples from the previous file. This matrix must be in csv format. 

#### Output
Intermediate results tables and the final signature table can be downloaded as csv files, using the last 8 cells of the NTF_ABIS.ipynb example notebook.

### DECONVOLUTION
#### Input files
The gene expression matrix of your samples must be in Excel format or csv format. The gene names must be gene symbols and there must be no duplicates, the genes must be in rows and the samples in columns.
The previously obtained reference signature must be in an Excel or csv format.

#### RNA-Seq deconvolution
For RNA-Seq deconvolution, the gene expression values must be TPM values. RNA-Seq deconvolution was implemented using Illumina HiSeq 2000 data.
We recommend using the 915 signature with RNA-Seq data.

#### Microarray deconvolution
For microarray deconvolution, the expression values should be derived from the selection of the maximum expression value of the probes encoding a single gene. 
We recommend using 415 signatures with microarray data.

#### Output
The output values correspond to the percentage of immune cell type in the range 0-100. If you add the frequencies for each cell type, you should ideally get a value close to 100.
