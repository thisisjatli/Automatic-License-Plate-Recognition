# Automatic License Plate Recognition

Split the whole process into three steps:
1. Detection: given a photo, our system will find where the license plate is
2. Segmentation: after getting the photo of the plate, do letter segmentation to separate the alphabets or numbers on the plate
3. Recognition: feed these letters into CNN models and classify them

### Detection
#### Faster RCNN object detection
* Dataset
    * Obtain the dataset of pictures containing license plates of Taiwan vehicles.
    * Use a labeling tool to label and box the objects.

* Pretrained model
    * Model name: faster_rcnn_inception_v2_coco
    * Tools: TensorFlow

* Result
    * Accuracy of above 98%
    * ![](https://i.imgur.com/4WUbT5R.png)

### Segmentation
#### Iterative Global Threshold (IGT)
* Continuously do the thresholding until a certain criterion is reached.
* After the global thresholding, segmented the image into smaller areas and do IGT on these regions. This is for further erasing the noise that still remains between objects we aim for.
* References
    * E. Kavallieratou and S. Stathis, “Adaptive binarization of historical document images,” in 18th International Conference on Pattern Recognition (ICPR’06), 3, 742–745, IEEE (2006)
    * E. Kavallieratou, “A binarization algorithm specialized on document images and photos.,” in ICDAR, 5, 463–467 (2005)
