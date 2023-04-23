# Understanding Deep Neural Networks requires rethinking generalization

## Experimenting with the CIFAR-10,ImageNet dataset to Validate Arguments discussed in the paper

* Randomization Test : One of the key findings of the paper is that deep neural networks easily fit random noise. To validate this, we are training a neural network on a dataset where the labels are randomly assigned and evaluate its performance on the original test set.The random label test can be performed in two ways:
    
    * Complete label shuffle: The labels are shuffled completely and the network is trained on the shuffled labels. The network is then evaluated on the original test set.
    * Shuffled pixels : The pixels of all the images are permuted using a single random permutation and the network is trained on the shuffled dataset. The network is then evaluated on the original test set.
    * Random Pixels : The pixels of all the images are replaced with random values and the network is trained on the shuffled dataset. The network is then evaluated on the original test set.
    * Gaussian Noise : The pixels of all the images are replaced with random values drawn from a Gaussian distribution and the network is trained on the shuffled dataset. The network is then evaluated on the original test set.


* Label Corruption : As the results of above experminets results in 0 test loss , Authors further test the theory of Random Noise Learning by varying the rate of label corruption and observing the effect on the test loss and time taken to converge. The models used for this experiment are Inception , AlexNet and MLP 1x512 . We will replicate the same experiment with the same models and datasets to validate the results of the paper.



* Explicit Regularization Significance : The Authors also argues that explicit regularization techniques L2 Regularization(Weight Decay) ,DropOut , Data Augementation etc , only marginaly improve generalization error , and that the network is able to fit the training data even without these techniques. To validate this, we are training a neural network on a dataset with and without these techniques and evaluate its performance on the original test set . If the there is no significant difference in the accuracy of the network trained with and without these techniques , it supports the argument that the network is able to fit the training data even without these techniques

* Implicit Regularization Significance : The Authors also argues that implicit regularization techniques like Early Stopping , Batch Normalization , Stocastic Gradient Descent etc , only marginaly improve generalization error , and that the network is able to fit the training data even without these techniques. To validate this, we are training a neural network on a dataset with and without these techniques and evaluate its performance on the original test set . If the there is no significant difference in the accuracy of the network trained with and without these techniques , it supports the argument that the network is able to fit the training data even without these techniques


