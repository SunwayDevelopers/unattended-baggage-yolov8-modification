# YOLOv8 Modification for Unattended Baggage Detection

## First Modification

### Add [BiFormer: Vision Transformer with Bi-Level Routing Attention](https://github.com/rayleizhu/BiFormer) into head

We will add this BiFormer attention mechanism into head

#### First Step : Change the Architecture

create a new yaml file called `yolov8-BiLevelRoutingAttention.yaml` under `ultralytics/cfg/models/v8` folder

and specify the modified architecture after adding BiFormer Attention Mechanism

#### Second Step: define the BiFormer Attention Mechanism code

add the `Biformer Attention` and `corresponding-attention-mechansim-into-Biform` code into `ultralytics/nn/modules/block.py`

#### Third Step: import the BiFormer Attention Mechanism into the yolov8 

import `Biformer Attention` into `ultralytics/modules/__init__.py` and also `ultralytics/nn/tasks.py` 


#### Fourth Step: Train the modified YOLOv8 model

Train a model using this modified `YOLOv8-BiLevelRoutingAttention` model

#### Note:

1) You need to pip install the local modified ultralytics into pip venv environment only can reflect the changes and use it. 
2) u can use it by `pip install -e .`
3) you no need to repip install it as it will constantly listen to ur changes.
4) Connect GCS in vertex AI

```
MY_BUCKET=compiled-training-data
cd ~/
gcsfuse --implicit-dirs --rename-dir-limit=100 --max-conns-per-host=100 $MY_BUCKET "/home/jupyter/gcs"

```