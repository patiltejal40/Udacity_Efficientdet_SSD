# Udacity_Efficientdet_SSD
Dataset : https://public.roboflow.com/object-detection/self-driving-car 

Model: 
EfficientDet achieves the best performance in the fewest training epochs among object detection model architectures,making it a highly scalable architecture especially
when operating with limited compute. EfficientDet is the object detection version of EfficientNet, building on the success EfficientNet has seen in image classification tasks.
EfficientNets come from a family of models that achieve a high performance on benchmark tasks while controlling for a number of efficiency parameters, 
such as model size and FLOPS. The network is delivered in a series of model sizes d0-d7, and the base model is thought to perform better than YOLOv3 with a smaller model size.

Model Implementation:

Preparing the Data:
Going straight from data collection to model training leads to suboptimal results. There may be problems with the data.
Even if there aren’t, applying image augmentation expands your dataset and reduces overfitting.
Formatting annotations to match the requirements of your model’s inputs (e.g. generating TFRecords for TensorFlow or a flat text file for some implementations of CNN).

Model and Training
We use a pytorch implementation of EfficientDet using the image detection library from Tessellate-Imaging for object detection. Our implementation uses the base
version of EfficientDet-d0. We train from the EfficientNet base backbone, without using a pretrained checkpoint for the detector.

Inference
We witness some fast inference on a few basic examples from our test set to see that our approach is heading in the right direction.

Export
We export our model weights to google drive for future utilization.

Next Steps
We will be exploring evaluation on custom RoboFlow datasets and objectives compared to yoloV3, including training time, inference time, model size, and performance.


Challenges in Deep Learning EfficientDet Addresses:

Before exploring the model, here are some key areas that have prevented image detection systems from being deployed to real life use cases.

Data Collection - With model architecture and pretrained checkpoints, EfficientDet cuts down on the amount of data required to generalize to a new domain.
Model Design and Hyper Parameterization - Once the data has been collected, machine learning engineers need to carefully set up the model design and tune a number of 
hyper parameters.
Training Time - the amount of time required to train the model on the gathered dataset. In the EfficientDet paper, this is measured in FLOPS (floating point operation per second).
Memory Footprint - Once the model is trained, how much memory is required to store the model weights when called upon for inference?
Inference Time - When the model is invoked, can it perform predictions quick enough to be used in a production setting?

EfficientNet: Motivation and Design
Recently, the Google Brain team released their own ConvNet model called EfficientNet. EfficientNet forms the backbone of the EfficientDet architecture,
so we will cover its design before continuing to the contributions of EfficientDet. EfficientNet set out to study the scaling process of ConvNet architectures.
There are many ways - it turns out 💭- that you can add more parameters to a ConvNet.
You can make each layer wider, you can make the number of layers deeper, you can input images at a higher resolution, or you can make a combination of these improvements.
As you can imagine, the exploration of all these possibilities can be quite tedious for machine learning researchers. EfficientNet set out to define an automatic procedure
for scaling ConvNet model architectures. The paper seeks to optimize downstream performance given free range over depth, width, and resolution while staying within the 
constraints of target memory and target FLOPs. 
They find that their scaling methodology improves the optimization of previous ConvNets as well as their EfficientNet architecture.

Referred blogs and sites:
https://blog.roboflow.com/object-tracking-how-to/
https://blog.roboflow.com/how-to-train-yolox-on-a-custom-dataset/
https://colab.research.google.com/drive/1ZmbeTro4SqT7h_TfW63MLdqbrCUk_1br#scrollTo=KwDS9qqBbMQa
https://colab.research.google.com/drive/1vzEDAX-3ol7gcZ7qmKuwn8zUld524sUZ#scrollTo=pURT5B8uVFgq
https://arxiv.org/abs/1911.09070
https://github.com/google/automl/tree/master/efficientdet
https://towardsdatascience.com/a-thorough-breakdown-of-efficientdet-for-object-detection-dc6a15788b73





