# Finetuning results
Data: train: 2500 birds RGB images (different sizes); target: 50 classes; scoring: categorical_accuracy.
#### SVM(sklearm.svm.SVC) on train reshaped (100, 100)
sklearm.svm.SVC default params

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 | ~ 0.02 | ~ 5-10 min

#### SVM(sklearm.svm.SVC) on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)
extracting time ~ 60 min

train_size | test_size | kernel |score | training time
------------ | ------------- | ---------- | ------------- | ----------
2000 | 500 | RBF | 0.01 | ~ 10 sec
2000 | 500 | linear | 0.70 | ~ 10 sec

#### Keras simple convolutional network on train reshaped (224, 224)
Architecture:
```python
Convolution2D(64, 3, 3, border_mode="same", activation="relu")
axPooling2D(pool_size=(3, 3))
Convolution2D(126, 3, 3, border_mode="same", activation="relu")
MaxPooling2D(pool_size=(3, 3))
Flatten()
Dense(250, activation="relu")
Dense(51, activation="softmax")
```
nb_epoch=10, batch_size=32

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 | ~ 0.02 | ~ 70 min

Other architectures give the same result.

#### Keras 2-dense-layers network on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)
extracting time ~ 60 min
nb_epoch=200, batch_size=60

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2250 | 250 | ~ 0.75 | < 2 min
2000 | 500 | ~ 0.73 | < 2 min
1750 | 750 | ~ 0.71 | < 2 min
1500 | 1000 | ~ 0.70 | < 2 min
1250 | 1250 | ~ 0.66 | < 2 min
1000 | 1500 | ~ 0.64 | < 2 min
750  | 1750 | ~ 0.60 | < 2 min
500  | 2000 | ~ 0.54 | < 2 min
250  | 2250 | ~ 0.40 | < 2 min
174  | 2326 | ~ 0.33 | < 2 min
99  | 2401 | ~ 0.27 | < 2 min
24 | 2476 | ~ 0.10 | < 2 min
