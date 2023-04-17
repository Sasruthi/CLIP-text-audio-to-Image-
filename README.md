# CLIP-text-audio-to-Image-
OBJECTIVE

Image Generation from Text description or Audio file .
The problem objective is to generate images from the summarized description which is either in text forms of audio form.
 As a result, a pictorial scenario is generated with the obtained keywords from the processed input context.
 
 DATASET
 
 Hosted version of Imagenette on the Hugging Face Datasets Hub .
Imagenette  has 13394 images in 10 classes   -  subset of Imagenet dataset .
Train split has 9469 images in 10 classes.
The full-sized images in the Imagenette dataset have a resolution of 256x256 pixels in RGB format has three color channels - red, green, and blue
An image has a total of 256x256x3 = 196608 pixels.

Text input can be given as prompt .
If a long text is given , it is summarized using a NLP user built function summary().
If Audio file is given in any format , it is converted to .wav form and the text is extracted using Google Speech recognition API and given to the model .
The CLIP model embeds the text prompt and find similarity with the images in a dimension .

PREPROCESSING 

Resizing (224*224 ,3) of the input image and Normalization .

Dual-encoder architecture with image encoder and a text encoder. The text encoder embeds text into a mathematical space while the image encoder embeds images into a mathematical space
Image encoding  - ViT – B/32 
Text encoding  - " transformer-based language model"  -> masked self attention transformer
				GPT 2
 CLIP is then trained to predict how likely the image corresponds to the text using contrastive pre-training.



