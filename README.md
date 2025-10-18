# MELO
## Introduction 
Understanding the impact that subtle variations (missense mutation, environmental change, ion chelation, ligand binding, etc.) have on protein structure helps to reveal their biological effects, but remained extremely challenging due to the difficulty in measuring and locating the changes in protein structure. Herein, a method entitled MELO was therefore constructed, which enable a systematic measurement based on residues’ geometric characteristics & relative distance and a high-throughput location of structural change based on secondary structure variation & protein segment shift. Compared with available methods, it was found best-performing in capturing the structure changes of various degrees of magnitude (some increases were >30%) and capable of precisely locating the regions of alterations for critical case studies. Moreover, it identified over 10,000 structural changes induced by subtle variation that existing methods failed to detect. An online server (https://idrblab.org/melo/) was further constructed to not only allow the users to upload their structures for comparison, but also provide all identified structure changes induced by subtle variation as accessible database. In summary, the method proposed and data provided here are critical for the structure prediction, function analysis, and rational design of proteins.
### The pipeline for measuring and locating secondary structure variations by calculating the Geometric Characteristics among residues within studied proteins
![MELO-Figure 1](https://github.com/user-attachments/assets/f8bc982e-820f-47b1-8b60-0c4462e41b8d)
### The pipeline for assessing structural segment shifts by calculating Relative Distances among residues within studied protein
![2(1)](https://github.com/user-attachments/assets/b823556f-8d23-4deb-9408-7af5f1729153)
## Installation
MELO provides an online computation service, a Linux version Python package, and a Windows executable program. The EXE program and the online version can be accessed at https://melo.prostco.net. This guide focuses on the installation and usage of the Linux version.
Before installing MELO, you need to install DSSP (Dictionary of Secondary Structure of Proteins). You can follow the DSSP installation instructions.
To install MELO, simply use pip:
```
pip install melopro
```
## Usage
Once MELO is installed, you can use it by running the **test.py** script.
### Example:
1.Prepare the required files:
  · protein_file (TEST.csv): This file should contain protein pairs in the following format:
```
protein1;protein2;chain1;chain2
6BYY,6BZ1,A;B,A;B
```
  · pdb_file: This folder should contain the corresponding PDB files for the proteins.
2.Create a Python script (test.py) with the following code:
```
from melo import melo

protein_file = "TEST.csv"  # Input protein pairs file
pdb_file = "test_pdb"      # Folder containing PDB files
save_folder = "result"     # Folder to save the results
threads = 1                # Set number of threads

melo(protein_file, pdb_file, save_folder, threads)
```
3.Run the script:
```
python test.py
```
The results will be saved in the result folder.
## Notes:
  · Ensure that the protein file is formatted correctly, with semicolons separating the protein names and chains.
  · You can adjust the number of threads based on your system's capabilities by changing the threads variable in the script.
