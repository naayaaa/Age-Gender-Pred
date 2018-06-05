# Age Gender Prediction				

This code repositort is used for finding and predicting from an image one or multiple human's gender and age(confidence scores provided for both age and gender).



![Example](https://github.com/adamzjk/Age-Gender-Pred/blob/master/example/lotr.jpg?raw=true)

### Requirements

- python3, pytorch
- `pip3 install --upgrade opencv-python, dlib, imutils, skimage`
- Download [FaceAligner]( http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2) and save `shape_predictor_68_face_landmarks.dat` in `models/`
- Download [FaceDetector]( http://dlib.net/files/mmod_human_face_detector.dat.bz2 ) and save `mmod_human_face_detector.dat` in `models/`

###  Examplar Usage

**Predicting images in val/ folder**

1. train the model using `python train.py`, weight will be stored in `models/`
2. or download pretrained weight from url[pending]
3. put your test image in `pics/val/`
4. run `python evaluate.py`

**real-time predicting**

just call `eval_live()` function in `evaluate.pt`

### Train/Test Pipeline

![Example](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/static/img/pipeline.png)

**Train**

1. Using **cleaned** [IMDB-WIKI dataset](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/)[1] for training (IMDB-WIKI dataset contains 50%+ mislabeled images[2]).
2. Using [FG-NET dataset](http://www-prima.inrialpes.fr/FGnet/html/benchmarks.html)[3] for testing.
3. Train a model based on ResNet-18, the output is 2 neuron represents probs of male&female and 100 neurons represents probs of being age 0-99.
4. Training detains can be found on src file `train.py` and configuration file `config.ini`

**Test**

1. detect and align faces using `dlib`
2. predict age and gender using ResNet-18 architecture

### Reference

[1] Rothe R, Timofte R, Van Gool L. Deep Expectation of Real and Apparent Age from a Single Image Without Facial Landmarks [J/OL]. International Journal of Computer Vision. 126 (2). 2018, Apr: 144–157. https://doi.org/10.1007/s11263-016-0940-3.

[2] Antipov G, Baccouche M, Berrani S-A et al. Effective training of convolutional neural networks for face-based gender and age prediction [J/OL]. Pattern Recognition. 72. 2017, December: 15–26. https: //hal.archives-ouvertes.fr/hal-01556389.

[3] Panis G, Lanitis A, Tsapatsoulis N et al. Overview of research on facial ageing using the FG-NET ageing database [J]. IET Biometrics. 5 (2). 2016: 37–46.





















