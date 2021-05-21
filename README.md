Performance on Fashion Mnist data:
a) Fully connected network (Dense layers) provided 89.50% accuracy with 0.35 loss without fitting issues
a) CNN model architecture designed by me provided 94% accuracy on test data with 0.18 loss without fitting issues.
b) VGG16 imagenet weights (untuned) provided 93% accuracy with 0.27 loss without fitting issues.
c) VGG16 imagenet weights (Till block 4) provided 93% accuracy with 0.18 loss without fitting issues.

Performance on CIFAR10 data:
Due to time constraint and constantly running out of GPU, I could run only 50 epochs for steps decay lr and 30 epochs for expoential decay. However, steps decay model got converged after 30 epochs based on training loss/accuracy. Thus, it is still considered comparable with other models with 100 epochs. Best model is with steps decay which provided 0.38 loss and 0.86 accuracy on test data. Also, it was comparatively time efficient. Base model is quick, but it suffers from severe overfit and validation loss shoots up after 20 epochs. As mentioned earlier, data augmentation provided better fit on original RGB image rather than converted RGB image as we did for VGG16 fashion-mnist. Step decay performs well may because gradient descent of loss takes bigger steps earlier towards minima and takes smaller steps once near minima. This helps model to find more deeper loss space. Cyclic lr also performs better, but due to its cyclic nature, it impacts test loss tends to be higher. However, other variants of decaying cyclic rates are worth trying. My favorite hyperparameter is learning rate, because it gives me indirect access to adjust the gradient which affects the weights and accuracy. Also, I would like to understand why sometimes loss and accuracy move is same direction whereas logically it should inverse relationship. I have observed that while evaluating model on test data, test loss is different for test data given in mini batches and entire test dataset.

![image](https://user-images.githubusercontent.com/79832198/119085822-ca098d00-ba47-11eb-9e64-6cb871780838.png)




