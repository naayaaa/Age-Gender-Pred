# Age Gender Prediction				

This code repositort is used for finding and predicting from an image one or multiple human's gender and age(confidence scores provided for both age and gender).

```
              |   
:-------------------------:|:-------------------------:
![Example](https://wx1.sinaimg.cn/mw690/98d135cfly1fs06rsr5adj20mx0cwtc9.jpg)  |  ![Example](https://wx1.sinaimg.cn/mw690/98d135cfly1fs06rsadytj20hs0bv415.jpg)
```

#### Requirements

- python3, pytorch
- `pip3 install --upgrade opencv-python, dlib, imutils, skimage`

#### Examplar Usage

1. train the model using `python train.py`, weight will be stored in `models/`
2. or download pretrained weight from url[pending]
3. put your test image in `pics/val/`
4. run `python evaluate.py`

### 