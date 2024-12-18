# Promoter Search in Bacteria

This repository contains the implementation of computational methods to identify the "WWWW" promoter sequence in the genome of *Azotobacter chroococcum*, a nitrogen-fixing bacterium. The project compares two methods—local alignment and statistical alignment—for promoter discovery.

## Project Overview

Promoters are critical DNA sequences located upstream of genes that initiate transcription by providing binding sites for RNA polymerase and regulatory proteins. Identifying these promoters is essential to understanding bacterial gene regulation and expression.

In this project:
- **Local Alignment Search**: Identifies regions of similarity between a query sequence (e.g., "WWWW") and target sequences.
- **Statistical Alignment**: Uses a position probability matrix (PPM) to identify statistically significant promoter patterns.

The study aims to compare the effectiveness of these methods in identifying "WWWW" promoters in the *A. chroococcum* genome, analyzing promoter percentages and positional distributions.

## Files in the Repository

### 1. `extract_genes.py`
This script:
- Reads the genome assembly and loci files in FASTA (.fna) and .gtf formats.
- Extracts gene sequences, selecting 100 base pairs upstream and 3 base pairs downstream of each gene.

### 2. `local_search.py`
Implements the local alignment search method:
- Converts adenine (A) and thymine (T) into "W" to represent the "WWWW" motif.
- Searches for promoters using a custom scoring matrix and traceback algorithm.
- Outputs the percentage of genes with potential promoters and their positional distributions.

### 3. `statistical_alignment.py`
Implements the statistical alignment method:
- Extracts upstream sequences and calculates a position probability matrix (PPM).
- Uses the PPM to calculate alignment scores and identifies potential promoters based on a normalized score threshold.
- Outputs promoter distributions.

### 4. `compare_methods.py`
- Compares the percentage of promoters detected and position distributions from both methods.
- Provides insights into the advantages and limitations of each approach.

## Key Results

- **Percentage of Promoters Detected**: Both methods identified promoters in 60.48% of sequences.
- **Positional Bias**: Local alignment introduced a positional bias based on proximity to genes, while statistical alignment provided a probabilistic, unbiased distribution.
- **Accuracy and Flexibility**: Statistical alignment was found to be more robust in capturing promoter distributions.

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/D-Vinod/Promoter_search_bacteria.git
   cd Promoter_search_bacteria
   ```

2. Install dependencies (e.g., Biopython):
   ```bash
   pip install -r requirements.txt
   ```

3. Run the scripts:
   - Extract genes:
     ```bash
     python extract_genes.py
     ```
   - Perform local alignment search:
     ```bash
     python local_search.py
     ```
   - Perform statistical alignment:
     ```bash
     python statistical_alignment.py
     ```
   - Compare methods:
     ```bash
     python compare_methods.py
     ```

## Dependencies
- Python 3.7+
- Biopython (for sequence handling)
- Matplotlib (for visualizing distributions)
- NumPy

## References
1. National Center for Biotechnology Information (NCBI) Genome Assembly for *Azotobacter chroococcum*: [Link](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_002220155.1/)
2. Biopython Library Documentation: [Link](https://biopython.org/)

## License
This project is open-source and licensed under the MIT License. See the `LICENSE` file for details.
