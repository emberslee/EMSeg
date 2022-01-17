# DeepEMSeg
## Introduction
[//]: DeepEMSeg is a deep learning based segmentation framework for intermediate resolution cryo-EM density maps

## Install

## Tutorial
1. symmetry detection (Phenix suite is needed):
```
phenix.map_symmetry MAP.mrc optimize_center=True symmetry=SYMMETRY
```
This command generates a symmetry matrix file named 'symmetry_from_map.ncs_spec' automatically.

2. backbone prediction
```
python pred.py -mi MAP.mrc -mo MAP_MC.mrc
```
This command predicts a main-chain probability map name MAP_MC.mrc from given input map MAP.mrc

3. run segmentation main program
```
./segmatch -mc MAP_MC.mrc -em MAP.mrc -t TH -n N > log
```
This command generates N regions with given threshold of given map MAP.mrc.
