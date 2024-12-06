# **SPIDER: A Semi-Supervised Continual Learning-based Network Intrusion Detection System**.
## Our paper Accepted to IEEE INFOCOM 2024 - IEEE Conference on Computer Communications
## Paper is available at https://ieeexplore.ieee.org/abstract/document/10621428

Network intrusion detection (NID) aims to identify unusual network traffic patterns (distribution shifts) that require NID systems to evolve continuously. While prior art emphasizes fully supervised annotated data-intensive continual learning methods for NID, semi-supervised continual learning (SSCL) methods require only limited annotated data. However, the inherent class imbalance (CI) in network traffic can significantly impact the performance of SSCL approaches. Previous approaches to tackle CI issues require storing a subset of labeled training samples from all past tasks in the memory for an extended duration, potentially raising privacy concerns. The proposed Semisupervised Privacy-preserving Intrusion detection with Drift-aware continual LEaRning (SPIDER) is a novel method that combines gradient projection memory (GPM) with SSCL to handle CI effectively without the requirement to store labeled samples from all of the previous tasks. We assess SPIDER’s performance against baselines on six intrusion detection benchmarks formed over a short period and the Anoshift benchmark spanning ten years, which includes natural distribution shifts. Additionally, we validate our approach on standard continual learning image classification benchmarks known for frequent distribution shifts compared to NID benchmarks. SPIDER achieves comparable performance to fully supervised and semisupervised baseline methods, while requiring a maximum of 20% annotated data and reducing the total training time by 2X.


## Setting the environment 

We recommend you create a  Python virtual environment and follow the instructions below
1. We provided the list of the necessary pre-requisites library to install in the requirements.txt
2. use  the "pip install -r requirements.txt" command to create the libraries

## Datasets
The preprocessed datasets can be downloaded from the [link](https://iith-my.sharepoint.com/:f:/g/personal/tbr_iith_ac_in/EjEONoT1ZupLlZS_dEHhticBZnuR5tQa8Cl96568UqTDgg?e=lYshEM)
The shared link contains preprocessed datasets (Network Intrusion Detection, Computer Vision) used in our work. 
## Extracting datasets files

1. unzip the preprocessed datasets.zip files
2. copy each dataset folder into the "datasets" directory in the **codebase** directory

##  Mapping the dataset files to code.
In case you face any issues while reading the dataset files, please set the appropriate dataset file path in the "metadata.py" file located in the codebase/utils directory.

For example, to set the correct dataset file path for the cifar10 dataset, configure the "path" key in  the metadata_dict_cifar10 dictionary in the metadata.py file.


## Running the code

To run the code, run the file with the main.py suffix. For example, to run ECBRS on the AnoShift dataset, use the following command.

1. python anoshift_ecbrs_main.py --gpu=GPU id --lr=learning rate(float) --w_d=weight decay(float)


To run baselines implemented in the Avalanche, you must run the file containing the suffix avalanche. For example, to run Anoshift, use the following command.

1. python anoshift_avalanche_main.py --gpu=GPU id --lr=learning rate(float) --w_d=weight decay(float) --cls=continual learning strategy (integer)
2. The continual learning strategy IDs for different algorithms are

| 0             | 1           | 2  |   3  | 4  |
| ------------- |:-------------:| -----:|-----:|-----:|
| EWC| GEM| A-GEM | GSS-greedy  | SI |


    
 ## Hyperparameter tuning

 To change the Hyperparameters, you need to make the changes in the configurations.py file located in codebase/utils/config/
 for example, to change the batch size of the cifar10 experiments, you need to change the line in configurations.py 

" root.cifar10.batch_size = 128"  




# Citation
Please cite this work in case you are referring to our work
```
@INPROCEEDINGS{10621428,
  author={Amalapuram, Suresh Kumar and Reddy Tamma, Bheemarjuna and Channappayya, Sumohana S.},
  booktitle={IEEE INFOCOM 2024 - IEEE Conference on Computer Communications}, 
  title={SPIDER: A Semi-Supervised Continual Learning-based Network Intrusion Detection System}, 
  year={2024},
  volume={},
  number={},
  pages={571-580},  
  doi={10.1109/INFOCOM52122.2024.10621428}}

```


