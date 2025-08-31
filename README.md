#  README

## 1. Data sources

This task is based on publicly available sequencing data from a study of **Metagenomics-assembled genomes reveal microbial metabolic adaptation to athalassohaline environment, the case Lake Barkol, China**. The dataset includes water and sediment samples which collected from Lake Barkol, Xinjiang, China. Metagenomic sequencing was performed on the **Illumina HiSeq 2500 platform** (Illumina Inc., San Diego, CA, United States).
The subsampled and raw reads FASTQs are stored in `data/` and are used as the inputs for the workflow.

---
## 2. How to download

All raw data used in this study is available through BioProject: PRJNA1200918, where the SRA accessions can be accessed as well. Approximately 60 Gb and 30 Gb of raw data was available so we selected one sample for this workflow.
the data for the selected sample was downloaded using the SRA Toolkit as per code below:
### SRA Toolkit

```bash
SRRS=("SRR31818008")

for SRR in "${SRRS[@]}"; do
    echo "Downloading $SRR ..."
    prefetch "$SRR"
    fastq-dump --gzip --split-files "$SRR"
done
```


---
## 3. Pre-processing / subsampling

INCLUDE THE METHOD YOU USED TO SUBSAMPLE, MINATURIZE, OR TRIM DOWN

1. **STEP 1** ...

Example:

```bash
CODE TO SUBSAMPLE
```


---

## 4. How the workflow works
DESCRIBE THE WORKFLOW HERE - NOTE THE BELOW ARE JUST EXAMPLES, REPLACE WITH YOUR OWN - YOURS CAN TAKE A VERY DIFFERENT FORMAT
The workflow files is stored in `workflow/`.

---

### Step 1 – Quality Control 

**Purpose:** Check the quality of the reads
**Tools:** `fastqc`, `multiqc`, 
**Inputs:** Subsampled FASTQ files (from `data/fastq_subsampled/`)
**Outputs:** Cleaned FASTQs, QC reports (`.html`)
**Command:**

```bash
fastqc *.fastq.gz
multiqc .
```

---

### Step 2 - Trimming

**Purpose:** removing adapters/primers
**Tools:** 'ivar'
**Inputs:** ...
**Outputs:** ...
**Command:**

---

### Step 3 – Mapping

**Purpose:** mapping reads to reference genome
**Tools:** 'bwa'
**Inputs:** ...
**Outputs:** ...
**Command:**

```bash
fastp --in1 sample.fastq.gz --out1 cleaned.fastq.gz ...
```

---

### Step 4 – Depth and coverage analysis

**Purpose:** mapping reads to reference genome
**Tools:** 'bwa'
**Inputs:** ...
**Outputs:** ...
**Command:**

```bash
fastp --in1 sample.fastq.gz --out1 cleaned.fastq.gz ...
```

---
**Outputs:** ...
**Command:**
**Outputs:** ...
**Comman
