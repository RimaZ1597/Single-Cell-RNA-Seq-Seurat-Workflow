# Single-Cell RNA-Seq Analysis of Alveolar Rhabdomyosarcoma (GSE113660) Using Seurat

This repository contains a full single-cell RNA-seq (scRNA-seq) analysis pipeline for the **Rh41 alveolar rhabdomyosarcoma cell line** from the GEO dataset **GSE113660**. The workflow uses **Seurat** in R to perform gene annotation, quality control, normalization, dimensionality reduction, clustering, UMAP visualization, and marker gene identification.

---

## Dataset Information
- **Cancer Type:** Alveolar Rhabdomyosarcoma  
- **Accession:** GSE113660  
- **Cell Count:** 6875  
- **Cell Line:** Rh41  
- **Gene Types:** Protein-Coding Genes (PCG) and lncRNAs  

---

## Pipeline Steps

### **1. Data Loading & Gene Annotation**
- Read raw expression matrix  
- Convert ENSEMBL IDs → Gene Symbols using **org.Hs.eg.db**  
- Remove duplicates and missing genes  

### **2. Create Seurat Object & Quality Control**
- Compute mitochondrial gene percentage  
- Violin plots for:
  - nFeature_RNA  
  - nCount_RNA  
  - percent.mt  

### **3. Normalization & Feature Selection**
- NormalizeData  
- FindVariableFeatures (2000 genes)  
- Identify top 10 HVGs  
- Plot variable features  

### **4. Dimensionality Reduction**
- ScaleData  
- PCA  
- PCA loadings, heatmaps  
- JackStraw significance test  
- ElbowPlot to choose PCs  

### **5. Clustering & Visualization**
- FindNeighbors  
- FindClusters (resolution = 0.5)  
- UMAP visualization  
- Save plots to PDF  

### **6. Marker Gene Discovery**
- Run FindAllMarkers  
- Export markers (`Markers_info.csv`)  
- Visualize with VlnPlot & FeaturePlot  

---

## Output Files
- **Plots.pdf** — QC, PCA, UMAP, marker plots  
- **Markers_info.csv** — cluster-specific marker genes  

---

## Dependencies
- Seurat  
- dplyr, tidyr, data.table  
- org.Hs.eg.db, AnnotationDbi  
- R ≥ 4.0  



