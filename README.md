# Finetuning results
Data: train: 2000 birds images (different sizes), target: 50 classes, test: 500 images.
#### SVM(sklearm.svm.SVC) on train reshaped (100, 100)

#### SVM(sklearm.svm.SVC) on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)

#### Keras simple convolutional network on train reshaped (120, 120)

#### Keras 2-dense-layers network on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)
train_size = 0.8 * 2500, test_size = 0.2 * 2500, score = 
train_size = 0.7 * 2500, test_size = 0.3 * 2500, score = 
train_size = 0.6 * 2500, test_size = 0.4 * 2500, score = 
train_size = 0.5 * 2500, test_size = 0.5 * 2500, score = 
train_size = 0.4 * 2500, test_size = 0.6 * 2500, score = 
train_size = 0.3 * 2500, test_size = 0.7 * 2500, score = 
train_size = 0.2 * 2500, test_size = 0.8 * 2500, score = 
train_size = 0.1 * 2500, test_size = 0.9 * 2500, score = 
