# Finetuning results
Data: train: 2000 birds images (different sizes), target: 50 classes, test: 500 images.
## SVM(sklearm.svm.SVC) on train reshaped (40, 40)

## SVM(sklearm.svm.SVC) on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)

## Keras simple convolutional network on train reshaped (120, 120)

## Keras 2-dense-layers network on features extracted with penult layer of pretrained VGG16 on ImageNet, train reshaped (224, 224)

