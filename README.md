# Building CNN from Scratch with Ensembles(Part A) and Transfer Learning with Fine Tuning and Feature Extraction(Part B)

### PART A: Convolutional Neural Networks:
Part A requires you to build a range of convolutional networks for tackling the Flowers dataset problem. It also requires you to explore the impact of data augmentation and investigate an ensemble technique.
<br>Please use the following optimizer for all models in Part A: tf.keras.optimizers.SGD(lr=0.01). You are free to use whatever learning rate you wish. I have used 0.01 in my code.
For each model you build you should plot the training and validation accuracy as well and the training and validation loss. You should also offer your interpretation of each of plots produced. Please include the graphic of the loss and accuracy as well as your interpretation in your report.
<br>(i) Implement a baseline CNN, which contains just a single convolutional layer, single pooling layer, fully connected layer and softmax layer.
Increase the number of layers in your CNN (the number of convolutional and pooling layers). You should implement at least three different CNN configurations (not including the baseline). In your report show the impact on the validation and training accuracy/loss values (inclusive of the baseline case). Compare and contrast the performance of your models in your report.
Investigate the implementation of data augmentation techniques for two of the above models (please select the two deepest models). In your report describe the impact(if any), of applying data augmentation on these models. How do you explain the impact of data augmentation? Does the selection of methods used as part of your data augmentation (such as cropping, flipping etc) have an influence on accuracy?
<br><br>
<br>(ii) Build a CNN ensemble containing a maximum of 10 base learners.
<br>In your report describe:
<br>▪ The methodology you used for implementing the ensemble.
<br>▪ The source of variability in your ensemble and why variability is an important factor when building an ensemble.
<br>▪ Compare the performance of the ensemble with each of the base learners.
During the training process of each base learner you should use checkpointing so that you can capture the base learner model with the lowest validation loss. Clearly there are many types of ensembles that you could build and explore.
The following are important factors to keep in mind when building your ensemble:
<br>• Colab has a limited amount of disk space and RAM. This can fill up very quickly depending on how you implement your ensemble and your checkpointing. A couple of points to help you minimize you RAM and disk storage space. (i) Train a specific base model, load the best checkpointed model and use it to predict the classes for the validation data. In other words, do not save each base model in a data structure and then do the predictions when you have collected all your base models (as this approach will consume significant amount of memory). Instead do the prediction for the current base model directly after you have trained the base model. (ii) When checkpointing during the model training process I suggest that you continually save the weights to the same file (not separate files). (iii) Also, if you using Colab you could consider saving your predictions for each base model to your Google drive. This means that if the training process for each model takes time then you don’t have to rerun everything from scratch if you change one base learner or if the session drops.
<br>• Please note that the maximum number of base learners is 10. However, if you are using larger networks in your ensemble you may find that you may end up using just 3 or 4 due to time constraints or computational resources. You will not be penalized for this.
<br>• Also, you will not be penalized if your ensemble doesn’t outperform the individual base learners.
<br>• There are a wide range of possible neural network ensembles that you could investigate. Appendix B provides a high level view of creating a very basic neural network ensemble (initializing a fixed architecture with new randomized weights). Successful implementation of this basic model is an acceptable approach. However, to achieve a very high grade for the ensemble you should aim to implement a more sophisticated and technically challenging ensemble (supported with evidence of research).
<br><br>
### PART B: Transfer Learning 
<br>
Part B focuses on transfer learning. You will be required to investigate and explore the impact of feature extraction and fine-tuning techniques.
<br>(i) Use a pre-trained CNN model (such as VGG or Inception models) as a feature extractor and pair its output with a secondary (standard) machine learning algorithm. For example, you could use a pretrained VGG16 network as a feature extractor and feed the extracted feature data into a logistic regression model. What is the impact on the validation and training accuracy values?
To grade well in this question, you should explore and examine appropriate variants of the above structure. For example, one appropriate variant would be to examine a selection of different secondary machine learning algorithms in order to improve the overall level of validation accuracy (for example would a Random Forest provide any performance advantage over a logistic regression unit). In your report you should include a description of the different variants you examined, a rationale for examining each variant and it’s impact on accuracy values.
<br><br>
<br>(ii) Explore the application of fine tuning as a method of transfer learning for the Flowers dataset.
Again, to grade well in this question you should include appropriate exploratory work. Your objective is to identify the best validation accuracy that you can achieve for the Flower dataset. Therefore, you should consider the variables involved when performing fine tuning as well as additional techniques you could use to improve performance. As in the previous question in your report include a description of the different variants you examined, a rationale for examining each variant and it’s impact on accuracy values.
