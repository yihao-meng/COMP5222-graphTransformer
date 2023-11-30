# Application of Graph Transformer on Fake News Detection
This repository introduces the use of HetTransformer model.
![avatar](/figures_and_tables/figure.png)

## Directory Structure
This is the intended directory sturcture after the completion of data collection and processing steps.
```
.
├── data/                               # Datasets and their processing scripts
|   ├── PHEME/                          # Collected and unzipped PHEME datapath
|   ├── README.md                       # Data pre-processing instructions
|   └── ...                             # Data pre-processing scripts
├── figures_and_tables/                 # Figures and tables in this README.md 
├── models/                             # Experiments-related scripts
|   ├── train_and_evaluation/           # The model training and evaluation code
|   ├── data_splits/                    # Train-val-test split used
|   ├── best_models/                    # The reserved model for users to run the training script to save their models
|   └── pre-trained/                    # The pre-trained models
├── README.md                           # Reproduction instructions
└── requirements.txt                    # Dependencies
```
Run the following commands to creat the directory sturcture needed.
```
mkdir data/processed_data data/rwr_results
```

## 0. Requirements
This repository is coded in `python==3.8.5`.
Please run the following command to install the other requirements from `requirements.txt`.
```
pip install -r requirements.txt
```

## 1. Dataset Collection

Run the following on command line to collect PHEME under `data/`, unzip it, and rename it.

```
cd data
wget -O PHEME.tar.bz2 "https://ndownloader.figshare.com/files/6453753"
tar -vxf PHEME.tar.bz2
mv pheme-rnr-dataset PHEME
cd ..
```

## 2. Data Pre-processing
Data pre-processing includes image fetching, image encoding, text encoding, graph construction, and the extraction of other features.
The details are described in [`data/README.md`](https://github.com/HetTransformer/HetTransformer-model/tree/main/data).


## 3. Model Training and evaluation
After generating batch files following step 1 and 2 in `data/processed_data/FakeNewsNet/PolitiFact/batch/`; `data/processed_data/FakeNewsNet/GossipCop/batch/`; `data/processed_data/PHEME/batch/` respectively. 

Download and place the n_neighbors.txt files following the instructions in [`models/README.md`](https://github.com/HetTransformer/HetTransformer-model/tree/main/models).

You can download the pre-trained models following the instructions in [`models/pre-trained/README.md`](https://github.com/HetTransformer/HetTransformer-model/tree/main/models/pre-trained).

You can also load the pre-trained models in `models/pre-trained/` following the evaluation scripts decribed under `models/train_and_evaluation/`.

Run scripts in `models/train_and_evaluation/` to train the model and get the evaluation results. You may need to rename the pre-trained models or change the PATH in train_and_evaluation codes if you do so. Since the default setting is to overwrite the models saved under `models/pre-trained/`.

## 4. Results
![avatar](/figures_and_tables/table.png)
