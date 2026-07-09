# Rare Disease Gene Dataset

Datasets linking rare diseases to their associated genes, extracted from [Orphadata](https://www.orphadata.com/) and [Ensembl](https://www.ensembl.org/).

**Download the data:** https://narayananr.github.io/rare_disease_genomics/

---

## Course Schedule

| Date | Session | Notebook | Open in Colab |
|------|---------|---------|---------------|
| Jun 6, 2026 | Class 1 | [Rare_Disease_Genes_Class_1.ipynb](notebooks/Rare_Disease_Genes_Class_1.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/narayananr/rare_disease_genomics/blob/main/notebooks/Rare_Disease_Genes_Class_1.ipynb) |
| Jun 6, 2026 | Homework 1 | [Rare_Disease_Genes_HW1.ipynb](notebooks/Rare_Disease_Genes_HW1.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/narayananr/rare_disease_genomics/blob/main/notebooks/Rare_Disease_Genes_HW1.ipynb) |
| Jun 13, 2026 | Class 2 | [Rare_Disease_Genes_Class_2.ipynb](notebooks/Rare_Disease_Genes_Class_2.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/narayananr/rare_disease_genomics/blob/main/notebooks/Rare_Disease_Genes_Class_2.ipynb) |
| Jul 9, 2026 | Homework 3 — Data Visualization | [Rare_Disease_Genes_HW3.ipynb](notebooks/Rare_Disease_Genes_HW3.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/narayananr/rare_disease_genomics/blob/main/notebooks/Rare_Disease_Genes_HW3.ipynb) |

---

## Getting Started

### Option 1: Use Google Colab (Easiest - No Installation!)

1. Click this link: **[Open in Google Colab](https://colab.research.google.com/github/narayananr/rare_disease_genomics/blob/main/notebooks/Rare_Disease_Genes_Class_1.ipynb)**
2. Sign in with your Google account
3. Click "Copy to Drive" to save your own copy
4. Start learning!

### Option 2: Download as ZIP (No Git Required)

1. Click the green **"Code"** button at the top of this page
2. Click **"Download ZIP"**
3. Extract the ZIP file to a folder on your computer
4. Open the `notebooks/Rare_Disease_Genes_Class_1.ipynb` file with Jupyter

### Option 3: Clone with Git

If you have Git installed, open Terminal (Mac/Linux) or Command Prompt (Windows) and run:

```bash
git clone https://github.com/narayananr/rare_disease_genomics.git
cd rare_disease_genomics
```

### Running the Notebook Locally

After downloading, you need Jupyter to run the notebook:

```bash
# Install Jupyter (if you don't have it)
pip install jupyter pandas matplotlib

# Open the notebook
cd rare_disease_genomics
jupyter notebook notebooks/Rare_Disease_Genes_Class_1.ipynb
```

---

## Project Structure

```
rare_disease_genomics/
├── data/                               # Datasets
│   ├── rare_gene_disease_dataset.csv
│   └── ensembl_genes.csv
├── scripts/                            # Python scripts to generate data
│   ├── fetch_rare_disease_genes.py
│   └── fetch_ensembl_genes.py
├── notebooks/                          # Course notebooks
│   └── Rare_Disease_Genes_Class_1.ipynb     # Class 1 (Jun 6, 2026)
├── index.html                          # GitHub Pages website
└── README.md
```

## Learn Data Analysis

**New to Python?** Start with Class 1 and work through the course notebooks.

📓 **[Rare Disease Genes — Class 1](notebooks/Rare_Disease_Genes_Class_1.ipynb)**

In Class 1 you'll learn:
- Loading and exploring CSV files with pandas
- Filtering the data to find specific diseases

Later sessions build on these basics:
- **[Class 2](notebooks/Rare_Disease_Genes_Class_2.ipynb)** — summarizing data, merging two datasets, and your first charts
- **[Homework 3 — Data Visualization](notebooks/Rare_Disease_Genes_HW3.ipynb)** — plotting in depth with matplotlib and seaborn: bar charts, box plots, scatter plots, histograms, and heatmaps

## Datasets

### Rare Disease Genes (`data/rare_gene_disease_dataset.csv`)

Maps rare diseases to their associated genes.

| Column | Description |
|--------|-------------|
| `disease` | Name of the rare disease |
| `gene_symbol` | Gene symbol (e.g., BRCA1) |
| `gene_full_name` | Full gene name |

**Sample data:**

| disease | gene_symbol | gene_full_name |
|---------|-------------|----------------|
| Multiple epiphyseal dysplasia-macrocephaly-facial dysmorphism syndrome | KIF7 | kinesin family member 7 |
| Brachydactyly-short stature-retinitis pigmentosa syndrome | CWC27 | CWC27 spliceosome associated cyclophilin |
| Aspartylglucosaminuria | AGA | aspartylglucosaminidase |

**Stats:** 4,128 diseases, 4,552 genes, 8,374 associations

### Ensembl Gene Annotations (`data/ensembl_genes.csv`)

Basic annotations for all human genes.

| Column | Description |
|--------|-------------|
| `ensembl_gene_id` | Unique Ensembl identifier (e.g., ENSG00000141510) |
| `gene_symbol` | Gene symbol |
| `chromosome` | Chromosome (1-22, X, Y, MT) |
| `start` / `end` | Genomic coordinates (bp) |
| `strand` | DNA strand (1 or -1) |
| `biotype` | Gene type (protein_coding, lncRNA, etc.) |
| `description` | Gene description |

**Sample data:**

| ensembl_gene_id | gene_symbol | chromosome | start | end | strand | biotype |
|-----------------|-------------|------------|-------|-----|--------|---------|
| ENSG00000210049 | MT-TF | MT | 577 | 647 | 1 | Mt_tRNA |
| ENSG00000211459 | MT-RNR1 | MT | 648 | 1601 | 1 | Mt_rRNA |
| ENSG00000210077 | MT-TV | MT | 1602 | 1670 | 1 | Mt_tRNA |

**Stats:** 78,691 human genes

## Usage

### Quick Start

Download the CSV files directly from the [GitHub Pages site](https://narayananr.github.io/rare_disease_genomics/).

### Regenerate Data

To regenerate the datasets from source:

```bash
# 1. Download Orphadata XML (required for rare disease genes)
# Get en_product6.xml from: https://www.orphadata.com/genes/

# 2. Generate rare disease gene associations
python scripts/fetch_rare_disease_genes.py

# 3. Generate Ensembl gene annotations
python scripts/fetch_ensembl_genes.py
```

**Requirements:** Python 3 with `requests` library

```bash
pip install requests
```

## Data Sources

- **Orphadata Product 6**: Genes associated with rare diseases
  - https://www.orphadata.com/genes/
  - Orphanet is the reference portal for rare diseases

- **Ensembl BioMart**: Human genome annotations
  - https://www.ensembl.org/biomart/
  - Comprehensive genome database

## Example: Find genes for a disease

```python
import pandas as pd

df = pd.read_csv('data/rare_gene_disease_dataset.csv')

# Find genes associated with cystic fibrosis
cf_genes = df[df['disease'].str.contains('cystic fibrosis', case=False)]
print(cf_genes)
```

Output:
```
            disease gene_symbol                         gene_full_name
41  Cystic fibrosis    SERPINA1                 serpin family A member 1
42  Cystic fibrosis     SLC26A9        solute carrier family 26 member 9
43  Cystic fibrosis     SLC6A14        solute carrier family 6 member 14
44  Cystic fibrosis      SLC9A3        solute carrier family 9 member A3
45  Cystic fibrosis        CFTR   CF transmembrane conductance regulator
...
(19 genes total)
```

## Example: Get gene details

```python
import pandas as pd

diseases = pd.read_csv('data/rare_gene_disease_dataset.csv')
genes = pd.read_csv('data/ensembl_genes.csv')

# Merge to get full gene details for rare disease genes
merged = diseases.merge(genes, on='gene_symbol', how='left')
print(merged[['disease', 'gene_symbol', 'chromosome', 'biotype']].head())
```

Output:
```
                                                                  disease gene_symbol chromosome         biotype
0  Multiple epiphyseal dysplasia-macrocephaly-facial dysmorphism syndrome        KIF7         15  protein_coding
1               Brachydactyly-short stature-retinitis pigmentosa syndrome       CWC27          5  protein_coding
2                                                  Aspartylglucosaminuria         AGA          4  protein_coding
3                                           Multiple sulfatase deficiency       SUMF1          3  protein_coding
4                                                       Beta-mannosidosis       MANBA          4  protein_coding
```

## License

The datasets are derived from:
- Orphadata: Available under [Creative Commons Attribution 4.0](https://www.orphadata.com/terms-of-use/)
- Ensembl: Available under open access terms

## Contributing

Issues and pull requests welcome at https://github.com/narayananr/rare_disease_genomics
