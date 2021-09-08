# MIATI
Paper: MIATI: Multi Interests And Temporal Information for Commodity Recommendation
## Prerequisites

- Python 3
- TensorFlow-GPU >= 1.8 (< 2.0)
- Faiss-GPU 

## Getting Started

### Installation

- Install TensorFlow-GPU 1.x

- Install Faiss-GPU based on the instructions here: https://github.com/facebookresearch/faiss/blob/master/INSTALL.md

- Clone this repo `git clone https://github.com/Sequential-Recommendation/MIATI`.

### Dataset

- Original links of datasets are:
  - JD: https://drive.google.com/file/d/19PemKrhA8j-RZj0i20_j4ERcnzaxl5JZ/view
  - taobao: https://tianchi.aliyun.com/dataset/dataDetail?dataId=649&userId=1
  - amazon: http://jmcauley.ucsd.edu/data/amazon/index.html

### Training

#### Training on the existing datasets

You can use `python src/train.py --dataset {dataset_name} --model_type {model_name}` to train a specific model on a dataset. Other hyperparameters can be found in the code. (If you share the server with others or you want to use the specific GPU(s), you may need to set `CUDA_VISIBLE_DEVICES`.) 

For example, you can use `python src/train.py --dataset JD --model_type MIATI` to train MIATI model on  dataset.

When training a ComiRec-DR model, you should set `--learning_rate 0.001`. 

#### Training on your own datasets

If you want to train models on your own dataset, you should prepare the following three(or four) files:
- train/valid/test file: Each line represents an interaction, which contains three numbers `<user_id>,<item_id>,<time_stamp>`.
- category file (optional): Each line contains two numbers `<item_id>,<cate_id>` used for computing diversity.

If you have ANY difficulties to get things working in the above steps, feel free to open an issue. You can expect a reply within 24 hours.

