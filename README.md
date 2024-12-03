# cap-gene-filtering

Gene filtering is based on filtering by locus group and locus type terms from the [HGNC Statistics & files](https://www.genenames.org/download/statistics-and-files/) and a [curated list of BCR and TCR genes](https://github.com/nealpsmith/neals_python_functions/tree/master/neals_python_functions/analysis/db).


CAP automatically filters out genes which are often over-expressed but biologically non-informative. The following genes are filtered out when reporting differentially expressed genes displayed on the heatmap:


**Mitochondrial genes**
- Genes from from genenames.org where “Chromosome == Mitochondrial”
- All genes where the “Gene group name” contains the word “mitochondria”
  
**Mitochondrial pseudogenes**
- All the pseudogenes associated with the genes selected in the mitochondrial genes section
- Example: For MT-RNR2 we filter “MT-RNR2 like 12 (pseudogene)”
  
**Ribosomal genes**
- All genes where the “Locus type” contains the word “ribosomal”
  
**Ribosomal pseudogenes**
- All pseudogenes, subset by “Locus Type == pseudogene,” that contain the word “ribosomal” in the “Approved name” column

**lncRNA genes**
- All genes where the “Locus type” contains “RNA, long non-coding”

**lncRNA pseudogenes**
- All the pseudogenes associated with the genes selected in the lncRNA genes section
- Example: For RN7SKP1, “RN7SK pseudogene 1” is filtered

**TCR genes**
- All the genes listed in [TCR genes](https://github.com/nealpsmith/neals_python_functions/blob/master/neals_python_functions/analysis/db/tcr_genes.tsv)  
- Excluding:
	- TRAV1-2 (MAIT marker)
	- TRGV9 and TRDV2 (circulating gdT marker)

**BCR genes**
- All the genes listed in [BCR genes](https://github.com/nealpsmith/neals_python_functions/blob/master/neals_python_functions/analysis/db/bcr_genes.tsv) 
