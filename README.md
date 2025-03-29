# Protein Subcellular Location Predictor

## Project Overview
This project implements a machine learning classifier to predict the subcellular location of eukaryotic proteins. The classifier categorizes proteins into five classes:

- **Cytosolic**: Proteins found within the cell but not inside organelles
- **Extracellular/Secreted**: Proteins transported out of the cell
- **Nuclear**: Proteins found within the cell's nucleus
- **Mitochondrial**: Proteins transported to the cell's mitochondria
- **Other**: Proteins that don't belong to any of the above categories

## Dataset
The model was trained on a dataset of non-homologous protein sequences:
- Cytosolic: 2,463 sequences
- Extracellular/Secreted: 1,236 sequences
- Mitochondrial: 1,023 sequences
- Nuclear: 2,736 sequences
- Other: 2,002 sequences (prokaryotic proteins that sometimes contaminate samples)

## Features
The classifier uses the following protein features:
- Sequence length
- Global amino acid composition (percentages of all 20 amino acids)
- Local amino acid composition (N-terminal and C-terminal regions)
- Physicochemical properties (isoelectric point, molecular weight)
- Sequence motifs and patterns

## Implementation
- **Language**: Python
- **Libraries**: 
  - Biopython (sequence processing)
  - Scikit-learn (machine learning)
  - Pandas & NumPy (data manipulation)
  - Matplotlib & Seaborn (visualization)

## Model Evaluation
The model was evaluated using:
- Cross-validation with appropriate train/test splits
- Metrics: Accuracy, F1 score, Matthews Correlation Coefficient
- Confidence estimation for predictions (High/Medium/Low)
- Performance on a blind challenge test set

## Usage
```bash
# Example usage
python predict_location.py input_sequence.fasta
```

## Output Format
The model returns predictions with confidence levels:
```
SEQID Location Confidence Level
```

Where:
- Location: Cyto, Extr, Nucl, Mito, or Othr
- Confidence: High, Medium, or Low

## Requirements
This tool is self-contained and requires only:
- Python 3.x
- Biopython
- Scikit-learn
- Other standard scientific Python libraries

## Project Structure
```
├── data/
│   ├── cytosolic.fasta
│   ├── extracellular.fasta
│   ├── mitochondrial.fasta
│   ├── nuclear.fasta
│   ├── other.fasta
│   └── challenge.fasta
├── src/
│   ├── feature_extraction.py
│   ├── model_training.py
│   ├── evaluation.py
│   └── predict_location.py
├── notebooks/
│   ├── exploratory_analysis.ipynb
│   └── model_evaluation.ipynb
├── results/
│   ├── figures/
│   └── challenge_predictions.txt
└── README.md
```

## Note
This project was completed as coursework for COMP0082, focusing on both prediction accuracy and explainability of the machine learning approach.
