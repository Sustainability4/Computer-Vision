Object detection is a process of detecting an object within an image or a video. For e.g one can know whether there is a dog in the image or not but if one
wants to identify whether where the dog is present in the image. Object detection will help you in localising the coordinates. Object detection is simply 
Image classification + Localisation. 

Few competition for object detection are : [COCO](https://competitions.codalab.org/competitions/20794#learn_the_details), [Pascal](http://host.robots.ox.ac.uk/pascal/VOC/),
[Imagenet](https://www.image-net.org/challenges/LSVRC/)

1. Bounding Boxes : Rectangular box around the objects in an image or a video are bounding boxes. In order to draw the bounding boxes, we initially
   considered two points. We may need a loss function in order to make a bounding box as close to the original box. Hence, we need to calculate the distance
   between the two boxes and reduce that distance between them. Another approach is when only the middle point of the rectangle with length and height 
   of the rectangle. Hence all the necessary information to form a rectangle is provided and its ensured that we have a complete bounding box. Bounding box
   follow the regression technique which helps them come as close to the true value as possible. 

2. Intersection over Union (IOU): One thing in order to predict as close to the actual value we may use a metrics of Intersection over Union as well. IOU 
   metrics is simply a ratio between the overlap area versus the total area of the two boxes. This will provide us a better prediction over the idea of close
   distances between the two boxes. We will define a threshold for IOU. On the basis of this threshold comparision we will finalise four buckets. 
   
   1. True Positive : Detection with IOU >= threshold
   2. False Positive : Detection with IOU < threshold
   3. False Negative : A ground truth is not detected. There was an object but was not detected. 
   4. True Negative will not apply in this case as we will be talking about teh connected misconnection which is quite not possible. 

3. Precision = TP/(TP+FP) = TP/All detections
4. Recall = TP/TP+FN = TP/All ground truths 

For COCO evaluation we use something called as 11 point interpolation average precision. One can understand average precision to be a scenario which is
favour when we have good precision and good recall. One can have a look [here](https://towardsdatascience.com/what-is-average-precision-in-object-detection-localization-algorithms-and-how-to-calculate-it-3f330efe697b#:~:text=Average%20precision%20is%20the%20area,is%20between%200%20to%201.)



