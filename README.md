# Siamese-Net-Signature-Forgery-Detection

Welcome you! This is an implementation of a Siamese-type CNN to detect signatures forgery. You can find one example of an siamese architecture below:

![alt text](https://github.com/ChristianCFranca/Siamese-Net-Signature-Forgery-Detection/blob/main/images/Siamese%20Network.png?raw=true)

The main principle in this type of CNN's is that we are not exactly worry about correctly classifing a image as `Dog` or `Cat` (for example) but rather measure the degree of similarity between the `Dog` and the `Cat` in such a way that cats will be found closely to each others in the embedding space and dogs will be founded far apart from cats but close to other dogs. This way, we can correctly classify a dog by just comparing it to another dog and vice-versa.

Following this logic, you shall find in my notebook `SiameseNetwork.ipynb` a implementation of a modified `Resnet18` in a siamese configuration solving the [ICDAR2011 Dataset](http://www.iapr-tc11.org/mediawiki/index.php/ICDAR_2011_Signature_Verification_Competition_(SigComp2011)).

![alt text](https://github.com/ChristianCFranca/Siamese-Net-Signature-Forgery-Detection/blob/main/images/EDA.PNG?raw=true)

The Loss function in this case shall be a distance-based function. The one selected was the `Constrastive Loss` or `Pairwise Ranking Loss`. Many are available for this field of problems and widely used like the `Triplet Loss`. The `Contrastive Loss` is a simpler approach.

The training of the modified architecture took about 1 hours to complete, yelding pretty good results for the loss function selected.

![alt text](https://github.com/ChristianCFranca/Siamese-Net-Signature-Forgery-Detection/blob/main/images/Training%20Loop.PNG?raw=true)
![alt text](https://github.com/ChristianCFranca/Siamese-Net-Signature-Forgery-Detection/blob/main/images/graphs.PNG?raw=true)

At the end we can see that similar signatures tend to stay closer to each other at a low `distance` value, and forged ones tend to be far away from the genuine ones.

![alt text](https://github.com/ChristianCFranca/Siamese-Net-Signature-Forgery-Detection/blob/main/images/results.PNG?raw=true)
