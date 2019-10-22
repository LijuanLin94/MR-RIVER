# MR-RIVER
Mendelian Randomization with Refined Instrumental Variable from Genetic Score (MR-RIVER) 


MR-RIVER, which extends score-based MR to summarized results and incorporates multiple correlated IVs, appeared to outperform the examined MR methods, and provided a more accurate and powerful means for the discovery of novel risk factors. 

# Example
```
# Load a mrdata
* bzx:         vector, SNP effects on risk factor
* bzx_se:	   vector, standard errors of bzx
* bzx_pval:    vector, p values for bzx
* bzx_maf:     vector, minor allele frequency of SNP	
* varx:        variance of risk factor
* bzx_n:	   sample size of GWAS for the risk factor
* bzy:         vector, SNP effects on disease
* bzy_se:      vector, standard errors of bzy
* bzy_pval:    vectorm p values of bzy
* snpid:       instrumental variables
* varz_x:      vector, variance of SNP
* n_ref:       sample size of GWAS for risk factor

load("mrdata.RData")

# Load LD correlation matrix
load("snpld.RData")

# Run MR-RIVER
* gwas_thresh:     threshold p-value to select instruments from GWAS for risk factor
* ld_r2_thresh:    LD r2 threshold to remove SNPs in high LD
* MAF:             flag for maf,defult is TRUE
* var:             flag for variance,defult is FALSE
* ldrho:           matrix, correlation between SNPs
MR_RIVER<-(MRdata = mrdata, ldrho =ldrho, gwas_thresh = 5e-8,
		   ld_r2_thresh = 0.5, MAF = TRUE, var=FALSE)
```
