# Promoter Search in Bacteria

This repository contains the implementation of computational methods to identify the "WWWW" promoter sequence in the genome of *Azotobacter chroococcum*, a nitrogen-fixing bacterium. The project compares two methods—local alignment and statistical alignment—for promoter discovery.

## Project Overview

Promoters are critical DNA sequences located upstream of genes that initiate transcription by providing binding sites for RNA polymerase and regulatory proteins. Identifying these promoters is essential to understanding bacterial gene regulation and expression.

In this project:
- **Local Alignment Search**: Identifies regions of similarity between a query sequence (e.g., "WWWW") and target sequences.
- **Statistical Alignment**: Uses a position probability matrix (PPM) to identify statistically significant promoter patterns.

The study aims to compare the effectiveness of these methods in identifying "WWWW" promoters in the *A. chroococcum* genome, analyzing promoter percentages and positional distributions.

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
   pip3 install -r biopython
   ```

3. Run the script:
   - Promoter_search.ipynb

## Dependencies
- Python 3
- Biopython (for sequence handling)
- Matplotlib (for visualizing distributions)
- NumPy

## References
1. National Center for Biotechnology Information (NCBI) Genome Assembly for *Azotobacter chroococcum*: [Link](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_002220155.1/)
2. Biopython Library Documentation: [Link](https://biopython.org/)

## License
This project is open-source and licensed under the MIT License. See the `LICENSE` file for details.
