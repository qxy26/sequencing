
# Nicking Site Analysis Pipeline

A Python-based pipeline for processing sequencing data and analyzing DNA nicking site preferences, including sequence extraction and sequence logo visualization.

---

## Overview

This project provides a workflow for analyzing nicking sites from merged sequencing reads. It includes:

* Filtering reads mapped to a target plasmid (pBlueScript II SK (+))
* Extracting sequence context around nicking sites
* Performing statistical analysis and visualization
* Generating sequence logos to reveal nucleotide preferences

---

## Features

* Read filtering based on reference plasmid mapping
* Extraction of 3′ and 5′ end sequence motifs
* Data analysis and visualization
* Sequence logo generation for motif discovery

---

## Requirements

* Python ≥ 3.8
* Biopython
* pandas
* matplotlib
* logomaker

Install dependencies:

```bash
pip install biopython pandas matplotlib logomaker
```

---

## Workflow

### 1. Sequence Processing

Merged sequencing reads are processed using **Biopython** to:

* Filter sequences
* Retain reads mapped to the target plasmid *pBlueScript II SK (+)*

---

### 2. Nicking Site Analysis

* Data processing is performed using **pandas**
* Visualization is generated using **matplotlib**

---

### 3. Sequence Extraction

Custom Python scripts are used to extract:

* The last **5 nucleotides at the 3′ end**, or
* The first **5 nucleotides at the 5′ end**

---

### 4. Sequence Logo Generation

* Sequence logos are generated using **logomaker**
* Used to identify nucleotide preferences at nicking sites

---

## Usage

```bash
python main.py \
  --input merged_reads.fasta \
  --output results/ \
  --mode 3prime
```

### Parameters

| Parameter | Description                              |
| --------- | ---------------------------------------- |
| --input   | Input merged sequence file               |
| --output  | Output directory                         |
| --mode    | `3prime` or `5prime` sequence extraction |

---

## Output

* Filtered sequences
* Extracted motif sequences
* Statistical plots
* Sequence logo figures

---

## Methods Summary

* Sequence filtering: **Biopython**
* Data analysis: **pandas**
* Visualization: **matplotlib**
* Motif visualization: **logomaker**

---

## Citation

If you use this pipeline, please cite:

```text
[Your paper citation here]
```

---

## Contributing

Contributions are welcome! Please submit a pull request or open an issue.

---

## License

MIT License


