# rvariant

This repository provides access to Variant Call Statistical Analysis, report of results and plotting options. 

We are gonna analise the VCA workflow to identify:

- which files are we gonna work with,
- where the statistical analysis should be applied,
- what a good report contains and
- which plots are the most relevant in this kind of analyses.

Elucidate a good workflow process is our main goal. 

# Directives for Variant Call Analysis (VCA)

## Where to Obtain Data

First, we need to determine the target population and then focus on retrieving a representative sample of sequences for comparison. Any of these fields are good for you?

### Target Fields

- Medical Genetics
- Cancer Research
- Evolutionary Biology
- Population Genetics

A meta-analysis focused to find multiple studies with similar research questions and data sequences could be useful to gain experience with the process. 

These test works over Whole-genome/exome sequencing (WGS/WES) or targeted sequencing data in fastQ format (Illumina, PacBio, Oxford Nanopore). 

Starting our data acquisition process at reputable repositories like EBI since they provide a wealth of sequencing data suitable for analysis. We could also try:

- PubMed
- Google Scholar
- Web of Science
- Scopus
- NCBI resources
- ResearchGate

## Data Wrangling

This stage involves a **Quality Control (QC) Process** and sequence alignment to a reference genome to determine their locations for variant calling. Additionally, consider sorting and indexing steps to optimize data access for subsequent stages. Marking duplicates is crucial to prevent false variant calls. A final step could be to perform local realignment around indels to enhance alignment accuracy, and also consider Base Quality Score Recalibration.

### Tools Used

- **Quality Control**: FastQC or Fastp for initial data quality assessment.
- **Alignment**: BWA, Bowtie2, or STAR.

- **Sorting and Indexing**: Picard or Samtools
- **Duplicate Marking**: Picard/Samtools

- **Local Realignment and Quality Score Recalibration**: GATK is a valuable tool for these purposes.

## Variant Calling

This step involves identifying genetic variants within the aligned and processed data.

### Tools Used

- GATK, Samtools, FreeBayes, and mpileup.

## Filtering

Establish a metric system to assess the importance of variants and retain high-quality ones while eliminating false positives. We can compare predicted functional impacts and other metrics (quality, read depth, allele frequency) using software tools.

### Tools Used

- GATK, Samtools, and FreeBayes.

## Annotation

Focus on functional consequences and gather information on the population frequency of variants. Explore potential links to clinical significance.

### Tools Used

- Annovar, VEO, or SnpEff.

## Reporting

In this section we should include a comprehensive list of identified variants, their annotations, and potential implications. Generate a Variant Call Format (VCF) file, and and assessesment of all Quality Control metrics for overall reliability (comparative table?).

### Tools Used

- Utilize BCFTools and VCFTools for reporting purposes.

## Validation

We can consider incorporating a framework for suggesting the design of PCR primers for future confirmatory experiments to verify the presence of variants in samples. Additionally, provide recommendations for interpreting the results, as this can be a challenging aspect of the analysis.

## Documentation

I suggest to use Oxygen for documentation.

# Publication

I want to submit this RPackage for a paper publication within LatinR netwrok. Would you like to proceed with this publication?
