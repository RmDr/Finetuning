# Finetuning results
Data: train: 2500 birds images (different sizes), target: 50 classes.
#### SVM(sklearm.svm.SVC) on train reshaped (100, 100)
sklearm.svm.SVC default params

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 | ~ 0.02 | ~ 5-10 min

#### SVM(sklearm.svm.SVC) on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)
extracting time ~ 60 min
sklearm.svm.SVC default params

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 |  |


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
0.9 * 2500 | 0.1 * 2500 | ~ 0.72 | < 2 min
0.8 * 2500 | 0.2 * 2500 | ~ 0.71 | < 2 min
0.7 * 2500 | 0.3 * 2500 | ~ 0.71 | < 2 min
0.6 * 2500 | 0.4 * 2500 |  | < 2 min
0.5 * 2500 | 0.5 * 2500 |  | < 2 min
0.4 * 2500 | 0.6 * 2500 |  | < 2 min
0.3 * 2500 | 0.7 * 2500 |  | < 2 min
0.2 * 2500 | 0.8 * 2500 |  | < 2 min
