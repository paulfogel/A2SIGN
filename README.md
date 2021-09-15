
INSTALLATION

Dependencies: some libraries are needed, to be installed using pip: pandas, numpy, sklearn, adjustText, scipy, matplotlib, seaborn, nmtf, IPython and tqdm.
A2Sign method is implemented in 2 Jupyter notebooks (see description below) available on GitHub and running on Python v3.6 and later.


EXAMPLE NOTEBOOKS

2 example Jupyter notebooks are provided:
 - NTF_ABIS.ipynb - example of signature definition from FACS filtrates (ABIS dataset).
 - deconvolution.ipynb - example of deconvolution on a bulk dataset using a reference signature previously obtained from FACS filtrates.
All data needed by the examples are in the "data" folder.


DEFINE REFERNCE MOLECULAR SIGNATURES

###Input files
1. Expression data from purified/sorted cell types.
The gene expression matrix of your samples must be in a Excel format. The gene names must be gene symbols and there should not be duplicates, genes should be in rows and samples in columns. 
2. Real proportions from FACS data for samples from previouse file. This matrix must be in a csv format. 

###Output
Intermediary results tables and final signature table can be downloaded as csv files using the last 8 cells of the NTF_ABIS.ipynb example notebook.


DECONVOLUTION
###Input files
The gene expression matrix of your samples must be in a Excel format or csv format. The gene names must be gene symbols and there should not be duplicates, genes should be in rows and samples in columns.
Reference signature previously obtained must be in a Excel format or csv format.


###RNA-Seq deconvolution
For RNA-Seq deconvolution the gene expression values must be TPM values. RNA-Seq deconvolution has been implemented using data from Illumina HiSeq 2000.
We recommend to use 915 signature with RNA-seq data.


###Microarray deconvolution
For microarray deconvolution, the expression values should derive from the selection of the maximum expression value from the probes encoding for a single gene. 
We recommend to use 415 signature with micro-array data.


####Output
The output values correspond to percentages of immune cell type, within the range of 0-100. When you sum the frequencies for each cell type, you should ideally get a value close to 100. 

