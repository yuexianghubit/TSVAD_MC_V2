# TSVAD_MC_V2

## Install
```
git clone https://github.com/yuexianghubit/TSVAD_MC.git
conda env create -f environment.yml
```


## Dataset
### 1. Download Alimeeting dataset (https://openslr.org/119/)
```
mkdir data
cd data
mkdir alimeeting
cd alimeeting
wget https://speech-lab-share-data.oss-cn-shanghai.aliyuncs.com/AliMeeting/openlr/Train_Ali_far.tar.gz
wget https://speech-lab-share-data.oss-cn-shanghai.aliyuncs.com/AliMeeting/openlr/Eval_Ali.tar.gz
tar -xzvf Train_Ali_far.tar.gz
tar -xzvf Eval_Ali.tar.gz
```

- Then make the dataset look like:
 ```
alimeeting
├── Train_Ali
│   ├── Train_Ali_far 
│     ├── audio_dir
│     ├── textgrid_dir
├── Eval_Ali
│   ├── Eval_Ali_far 
│     ├── audio_dir
│     ├── textgrid_dir
```

- run scripts/preprocess_ali.sh and then the dataset should look like
```
alimeeting 
├── Train_Ali
│   ├── Train_Ali_far 
│     ├── audio_dir
│     ├── target_audio
│     ├── target_embedding
│     ├── textgrid_dir
│     ├── Train.json
├── Eval_Ali
│   ├── Eval_Ali_far 
│     ├── audio_dir
│     ├── target_audio
│     ├── target_embedding
│     ├── textgrid_dir
│     ├── Eval.json
```



## Multi-Channel TS-VAD
### Train
```
bash run_ali_mc.sh # This will use only alimeeting dataset for training.
bash run_ali_ami_mc.sh # This will use alimeeting and ami datasets for training.
```
