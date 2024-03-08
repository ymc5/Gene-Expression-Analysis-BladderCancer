# Gene-Expression-Analysis-BladderCancer
Comprehensive analysis combining gene expression, enrichment, immuno-oncology, and pathway analyses to identify key factors in bladder cancer progression


## Objective
This comprehensive analysis aims to evaluate the difference in gene expression between normal tissue and primary invasive type bladder cancer patient samples. The analysis includes three main steps: gene expression analysis using t-test (Step 1), enrichment analysis of differentially expressed genes (DEGs) (Step 2), and immuno-oncology analysis using CIBERSORT X platform (Step 3). Additionally, a pathway analysis based on DEG and enrichment analysis results is conducted to identify relevant pathways associated with bladder cancer (Step 4).

---

## Step 1: Gene Expression Analysis

### Objective
Evaluate the difference in gene expression between normal tissue and primary invasive type bladder cancer patient samples.

### Method
- **Dataset:** Contains patient sample information and gene expression data.
- **Analysis:** T-test was conducted to filter genes significantly differently expressed in normal and bladder cancer samples.

### Analysis Steps
1. **Check Clinical & Molecular Data:**
   - Clinical Data: "20191105_BC_ClinData_233rows.csv"
   - Molecular Data (Gene Data): "20191105_BC_GeneExpData_withAddno_233.tsv"
   - Link data using GSMid (Sample ID).
2. **Clean/Filter Data & Identify Groups:**
   - Filter clinical data to include only control (normal bladder mucosae) and comparison (primary_BC_invasive) groups.
   - Final molecular data description:
     - Control group: 43148 genes with 10 variables
     - Comparison group: 43148 genes with 62 variables
3. **Sanity Check:**
   - Compare GSMid values between control and comparison groups to confirm data integrity.
4. **Preparing Data for T-Test:**
   - Confirm absence of missing values.
5. **Call Function for T-Test:**
   - Import R script "fnTTest.R".
6. **T-Test Result File Generation:**
   - Generate "TTest_Final_Invasive_(Comp).vs._control_(Base).TTest.csv".
   - Further filter genes based on p-value and fold change.

### Summary
After Step 1 analysis, 633 genes were identified as differentially expressed between control and comparison groups.

---

## Step 2: Enrichment Analysis

### Objective
Identify pathways affected by differentially expressed genes (DEGs) from Step 1.

### Method
- Genes from Step 1 were used for enrichment analysis using EnrichR package.

### Analysis Steps
1. **Import Packages & File for Analysis:**
   - Packages: enrichR, openxlsx
   - File: "2023-EnrichR-Databases.txt"
2. **Import T-Test Results (Filtered DEG List):**
   - Import csv file containing filtered genes.
3. **Load Database & Run Enrichment:**
   - Call enrichment R script to conduct analysis and create output file.

### Summary
The outcome of Step 2 analysis is an Excel file containing enriched pathways from Reactome, WikiPathway, and Gene Ontology databases.

---

## Step 3: Immuno-Oncology Analysis

### Objective
Compare immune cell profiles between normal and bladder cancer samples using CIBERSORT X platform.

### Method
Upload normal tissue and primary invasive type bladder cancer tissue files to CIBERSORT X for analysis.

### Analysis Steps
1. **Upload Normal & Tumor Tissue Files**
2. **Run Analysis for Normal Sample**
3. **Check Normal Sample Job Results**
4. **Run Analysis for Tumor Sample**
5. **Check Tumor Sample Job Results**
6. **Sort Top 5 Immune Cells for Each Group**

### Summary
Significant differences in immune cell profiles, particularly dendritic cells, CD4 memory T cells, and regulatory T cells, were identified through CIBERSORT X analysis.

---

## Step 4: Pathway Analysis

### Objective
Conduct a comprehensive analysis based on DEG, enrichment analysis, and CIBERSORT results to identify relevant pathways associated with bladder cancer.

### Method
Analyze pathways from enrichment analysis, filtering for relevance to CIBERSORT results and bladder cancer.

### Analysis Steps
1. **CIBERSORT Results:**
   - Identify top 5 expressed cells in normal and bladder cancer samples.
   - Compare cells with higher difference in expression levels.
2. **Pathway Review:**
   - Select pathways relevant to CIBERSORT results and bladder cancer.
3. **Pathway Final Selection:**
   - Conduct further research to examine association of selected pathways with bladder cancer.

### Summary
Selected pathways, including Cap-dependent Translation Initiation, RAC2 GTPase Cycle, Interferon Gamma Signaling, Interleukin-6-Mediated Signaling Pathway, and Antigen Processing And Presentation Of Exogenous Peptide Antigen Via MHC Class II, were identified as relevant to bladder cancer based on pathway research and literature review.

---

