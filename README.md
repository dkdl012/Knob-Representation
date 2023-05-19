# TMP Repository

## Requirements
- lifelines
- pytorch == 1.7.0
- python >= 3.8
### SMAC library
- https://automl.github.io/SMAC3/main/index.html
#### How to install
<pre>
conda install gxx_linux-64 gcc_linux-64 swig
pip install smac
</pre>

## TRAIN
### Run main.py to train the entire model. Paser explanation as below,
<pre>
target      : target workload number  
tf          : using teacher forcing, if not specify this, the model will be trained by non-teacher forcing  
train       : mode of train  
eval        : mode of train using pre-trained model(.pt)  
model_path  : if using eval mode, add pre-trained model path  
batch_size  : batch size for dataset
hidden_size : hidden size of the model  
lr          : learning rate of the model  
generation  : the counts of generation in Genetic Algorithm  
pool        : size of pool in genetic algorithm
optimization: choose optimization algorithm ['ga', 'smac']
</pre>
* #### Training the model
```
python main.py --target ${target_idx} --tf --train --hidden_size ${hidden_size} --lr ${learning_rate} \
--generation ${generation_num}
```
* #### Training with pre-trained model path
```
python main.py --target {target number} --tf --eval --model_path {model_path} \
--generation {generation number in genetic algorithm}
```
