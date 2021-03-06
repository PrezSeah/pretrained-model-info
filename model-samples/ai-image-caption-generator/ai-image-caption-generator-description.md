
**AI Model : AI Image Caption Generator - Description**

**Overview**

This model generates captions from a fixed vocabulary that describe the contents of images in the COCO Dataset. The model consists of an encoder model - a deep convolutional net using the Inception-v3 architecture trained on ImageNet-2012 data - and a decoder model - an LSTM network that is trained conditioned on the encoding from the image encoder model. The input to the model is an image, and the output is a sentence describing the image content.  
  
The model is based on the Show and Tell Image Caption Generator Model.

**Model Metadata**

Domain : Vision  
Application : Image Caption Generator  
Industry : General  
Framework : Tensorflow  
Training Data : COCO Dataset  
Input Data Format : Images

**Dockehub Link**

[https://hub.docker.com/r/codait/max-image-caption-generator](https://hub.docker.com/r/codait/max-image-caption-generator)

**Deployment**

Deployment from dockerhub:  
docker run -it -p 5000:5000 codait/max-image-caption-generator

**Model Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F image=@football.PNG;type\=image/png

**Model Testing Python Code**

· Download the test image from the link :  
[https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-caption-generator/sample\_input](https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-caption-generator/sample_input)

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('football.PNG', open('sample\_input/football.PNG', 'rb'), 'image/png')})

res.content

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-caption-generator/ai-image-caption-generator-description_files/image002.jpg)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "index": "0",

 "caption": "a soccer player is kicking a soccer ball .",

 "probability": 0.0018393118846582502

 },

 {

 "index": "1",

 "caption": "a soccer player is kicking a soccer ball",

 "probability": 0.0004151401108329707

 },

 {

 "index": "2",

 "caption": "a soccer player is kicking a ball on the field .",

 "probability": 0.00022804233787542945

 }

 \]

}
