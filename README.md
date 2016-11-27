# Finetuning results
Data: train: 2000 birds images (different sizes), target: 50 classes, test: 500 images.
#### SVM(sklearm.svm.SVC) on train reshaped (100, 100)

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 | 0.006 | ~ 5-10 min

worse than random

#### SVM(sklearm.svm.SVC) on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 | 0.006 | ~ 5-10 min


#### Keras simple convolutional network on train reshaped (224, 224)
nb_epoch=10, batch_size=4

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
2000 | 500 | ? | ~ 70 min

#### Keras 2-dense-layers network on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)

nb_epoch=100, batch_size=65

train_size | test_size | score | training time
------------ | ------------- | ------------- | ----------
0.8 * 2500 | 0.2 * 2500 | 
0.7 * 2500 | 0.3 * 2500 | 
0.6 * 2500 | 0.4 * 2500 | 
0.5 * 2500 | 0.5 * 2500 | 
0.4 * 2500 | 0.6 * 2500 | 
0.3 * 2500 | 0.7 * 2500 | 
0.2 * 2500 | 0.8 * 2500 | 
