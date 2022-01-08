# Preligens Data Challenge 2021
(From the Challenge Website https://challengedata.ens.fr/participants/challenges/48/:) "This challenge tackles the problem of land cover predictive modeling from aerial images taken from space. The goal of this challenge is to predict, for an input satellite image in which every pixel is assigned to a land cover class, the proportion of each class of land cover in the image.

The input data contains 256x256 pixel images of four bands covering the visible spectrum as well as near-infrared (R-G-B-NIR). Those images are extracted from larger Sentinel-2 images over the European continent. Every pixel covers a 10 meters square area. In addition, a segmentation mask is provided for every image, where each pixel contains one land cover label, encoded as an integer. The land cover labels are drawn from the ten different classes that follow (the corresponding class label index is given in parenthesis):

- no_data (0)
- clouds (1),
- artificial surfaces and construction (2),
- cultivated areas (3),
- broadleaf tree cover (4),
- coniferous tree cover (5),
- herbaceous vegetation (6),
- natural material surfaces (7),
- permanent snow-covered surfaces (8),
- water bodies (9).

"

I achieved a score of 0.0619 employing the pretrained ResNet50 on a 4-channel input with an 8-label class output (each output between 0 and 1, summing to 1). For the relatively small dataset I used data augmentation, which improved performance significantly. The criterion was the KL loss.
