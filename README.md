
# Nicking Site Analysis Pipeline

A Python-based pipeline for processing sequencing data and analyzing DNA nicking site preferences, including sequence extraction and sequence logo visualization.

## Overview

This project provides a workflow for analyzing nicking sites from merged sequencing reads. It includes:

* Filtering reads mapped to a target plasmid (pBlueScript II SK (+))
* Extracting sequence context around nicking sites
* Performing statistical analysis and visualization
* Generating sequence logos to reveal nucleotide preferences

## Features

* Read filtering based on reference plasmid mapping
* Extraction of 3′ and 5′ end sequence motifs
* Data analysis and visualization
* Sequence logo generation for motif discovery

## Requirements

* Python ≥ 3.8
* Biopython
* collections
* pandas
* matplotlib
* logomaker
* math

## Workflow

### 1. Sequence Processing

Merged sequencing reads are processed using **Biopython** to:

* Filter sequences
* Retain reads mapped to the target plasmid *pBlueScript II SK (+)*

### 2. Nicking Site Analysis

* Data processing is performed using **pandas**
* Visualization is generated using **matplotlib**

### 3. Sequence Extraction

Custom Python scripts are used to extract:

* The last **5 nucleotides at the 3′ end**, or
* The first **5 nucleotides at the 5′ end**

### 4. Sequence Logo Generation

* Sequence logos are generated using **logomaker**
* Used to identify nucleotide preferences at nicking sites

## Usage

Open seq-plasmid.ipynb and follow the steps inside, all output files should be checked step by step to make sure the format and files'name are right, be aware of the manual processing in Microsoft Excel.

Fragment file should be processed in both forward and reverse direcrion.

### Parameters

· for sequence matching

| Parameter      | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| --fasta_file   | Input raw fragments.fasta file                               |
| --plasmid_file | input plasmid.fasta file                                     |
| --output_csv   | csv file of matched sequences, including id, length and start&end positions |

· for break site positions and frequency calculating

| Parameter     | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| --input_csv   | matched and filtered sequences‘ id, length and start&end positions that can be concatenated |
| --bar_csv_out | csv file cotaining all break sites'frequency                 |

·for extracting FASTA sequences corresponding to entries passing the secondary filtering in the CSV file

| Parameter         | Description                         |
| ----------------- | ----------------------------------- |
| --fragments_fasta | Input filtered fragments.fasta file |
| --plasmid_file    | input plasmid.fasta file            |
| --output_fasta    | selected sequences                  |

·for extracting FASTA sequences corresponding to entries passing the secondary filtering in the CSV file

| Parameter      | Description                         |
| -------------- | ----------------------------------- |
| --input_fasta  | Input filtered fragments.fasta file |
| --output_fasta | extracted last *bp of fasta file    |
| --bp_len       | target bp_length                    |

·for fasta merging

| Parameter     | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| --file1       | extracted last *bp fasta file of sequences on forward direction |
| --file2       | extracted last *bp fasta file of sequences on reverse direction |
| --output_file | merged fasta file                                            |

·for logo creating

| Parameter    | Description       |
| ------------ | ----------------- |
| --fasta_file | merged fasta file |

## Output

* Filtered sequences
* 3' and 5' motifs' sequences

* Statistical  of break sites'positions and frequency
* Sequence logo figures





