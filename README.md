# 📊 iTrust SWaT Dataset Preprocess Tool

This is a tool for iTrust SWaT dataset preprocessing, including dataset details introduction, dataset visulization, dataset processing and some pytorch utils. 

## 💡 Introduction

iTrust Secure Water Treatment (SWaT) dataset is a famous and widely used dataset, mostly in anomaly detection field. For more details about this dataset, please refer to the official site for SWaT dataset: [https://itrust.sutd.edu.sg/testbeds/secure-water-treatment-swat/](https://itrust.sutd.edu.sg/testbeds/secure-water-treatment-swat/)

Since SWaT is originally collected dataset, by using it, we should do some preprocessing. Here we provide a tool to help you do this. Here we mostly forcus on SWaT 2015 dataset since it provides more clear attack informations. About other years data, we will keep updating. Here are features about our tool. 

Features: 

- Data visulization: we visulized the dataset, with marking anomaly parts, which is clear to check data patterns. 
- Excel tools: we provide some tools to help you read excel elegantly, like reading attack lists and return attacks within what period you choose. 
- Spectral residual preprocessing: since the SWaT dataset has obvious cycle pattern, we apply spectral residual method to help us remove redundancy. 
- Pytorch dataset class: we provide pytorch dataset class, can be applied in time-series anomaly detection trainning. 

## 🔧 Environment 

``` 
Python Version: 3.6 or later
Python Packages: jupyterlab, torch, numpy, pandas, matplotlib, sklearn
```

## 📁 Structure

```
.
├── data/
│   ├── swat-2015-data.csv
│   ├── swat-2015-data.npy
│   └── swat-2015-attack.xlsx
├── fig
├── notebook/
│   ├── swat-2015-info.ipynb
│   ├── swat-2015-process.ipynb
│   └── swat-2015-dataset.ipynb
├── src/
│   ├── silency.py
│   └── util.py
└── README.md
```

- `data/`: all dataset files will be here
    - `swat-2015-data.csv`: original dataset, transferred from xlsx file
    - `swat-2015-data.npy`: transferred dataset
    - `swat-2015-attack.xlsx`: original attack information
- `fig/`: result figures will be here
- `notebook/`: preprocess in notebook format
    - `swat-2015-info.ipynb`: introduction about the dataset, including basic information and visulization
    - `swat-2015-process.ipynb`: main preprocess on the dataset, including normalization and SR method
    - `swat-2015-dataset.ipynb`: about using the torch dataset class tool
- `script/`: preprocess in script format
- `src/`: source code of tools 

## 📖 How to use

**Step 1.** [Clone]() or [Download]() this repository.

**Step 2.** Run `notebook/swat-2015-info.ipynb` to get a basic idea about the dataset. More details are included in the notebook. 

**Step 3.** Run `notebook/swat-2015-process.ipynb` to preprocess the dataset. More details are included in the notebook. 

**Step 4.** Run `notebook/swat-2015-dataset.ipynb` to check generated torch dataset. More details are included in the notebook. 

**Step 5.** Use scrpts in your project to get dataset preprocessed. 

## 📋 Examples

**1.** Visulization for the original dataset. Orange lines mean anomaly part. 

![Visulization for the original dataset](fig/swat-2015.png)

**2.** Spectral on one feature as an example. 

![SR Sample](fig/swat-2015-sr-sample.png)

**3.** Spectral on all dataset features.

![SR](fig/swat-2015-sr.png)

## 📚 References

[1]. Hou, Xiaodi, and Liqing Zhang. **"Saliency detection: A spectral residual approach."** *2007 IEEE Conference on computer vision and pattern recognition.* Ieee, 2007.
