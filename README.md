# MXene-database
# The AFT framework and MXene database

# All structures and Efa data are contained in the .rar file
# Folder "1x1basemodel" and "2x2basemodel" are the well-trained models for predicting the data sets (.json) in the .rar file.
# Folder "MXene1X1*" to "MXene4X4*" includes all the structure mentioned in our paper.

# Here is a simple example for testing
"""
from pymatgen.core import Structure
from maml.models import AtomSets
from maml.describers import MEGNetSite
from sklearn.metrics import r2_score

with open("Data and model\MX4X4_Efa_without.json","r") as f:  # Attention: please ensure your path is correct
    data = json.load(f)
struct = [Structure.from_file(i) for i in data["structures"]]
target = data["Ef"]

model = AtomSets()
model_test = model.from_dir("Data and model\2x2basemodel")
describer = MEGNetSite(level=2)

features = describer.transform(struct)
valid_targets = model_test._predict(features)
R2 = r2_score(target, valid_targets)
print("- R2: ",R2)
"""


```
Song, Z.H., Niu, X.B., Chen, H.Y. 
Leveraging all-fixed transfer framework to predict interpretable
formation energy of MXene with hybrid terminals.
```
