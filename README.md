## Env

```bash
conda create -n celeba python=3.8
conda activate celeba
pip install -r requirements.txt
```

## CelebA HQ 256

1. run

```.bash
wget https://openaipublic.azureedge.net/glow-demo/data/celeba-tfr.tar
```

To download the zip file for CelebA HQ 256, which is about 4GB.

2. Move the zip file into `../data/celeba`, and go into the directory `data/`.

unzip: 

```.bash
tar -xvf celeba-tfr.tar
```

3.
run
```shell script
DATA_DIR=$(pwd)
CODE_DIR=../celebahq256
cd $CODE_DIR/scripts
python convert_tfrecord_to_lmdb.py --dataset=celeba --tfr_path=$DATA_DIR/celeba/celeba-tfr --lmdb_path=$DATA_DIR/celeba/celeba-lmdb --split=train
python convert_tfrecord_to_lmdb.py --dataset=celeba --tfr_path=$DATA_DIR/celeba/celeba-tfr --lmdb_path=$DATA_DIR/celeba/celeba-lmdb --split=validation
```
