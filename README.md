# YOLOv8 Modification for Unattended Baggage Detection

## First Modification

### Add [BiFormer: Vision Transformer with Bi-Level Routing Attention](https://github.com/rayleizhu/BiFormer) into head

We will add this BiFormer attention mechanism into head

#### First Step : Change the Architecture

create a new yaml file called `yolov8-BiLevelRoutingAttention.yaml` under `ultralytics/cfg/models/v8` folder

and specify the modified architecture after adding BiFormer Attention Mechanism

#### Second Step: define the BiFormer Attention Mechanism code

add the `Biformer Attention` code into `ultralytics/nn/modules/block.py`

#### Third Step: import the BiFormer Attention Mechanism into the yolov8 

import `Biformer Attention` into `ultralytics/modules/__init__.py` and also `ultralytics/nn/tasks.py` 


#### Fourth Step: Train the modified YOLOv8 model

Train a model using this modified `YOLOv8-BiLevelRoutingAttention` model