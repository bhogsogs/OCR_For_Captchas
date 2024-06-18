# OCR_For_Captchas

 OCR (Optical Character Recognition) is the technology that enables the conversion of images
 containing printed or handwritten text into machine-readable text.
 Several Machine Learning-based approaches  have been proposed for OCR, that include
 utilizing object detection models like YoLOv5 and DBNet for text localization, and
 employing encoder-decoder architectures, often based on CNNs and RNNs, for text
 recognition. Recent advancements integrate Transformers for improved accuracy, with
 potential exploration of pre-trained CV and NLP models to further enhance performance.

 # Problem Statement

 We were provided with the following problem statement :
Given an image of captcha, you have to train a model which is capable of predicting the
 characters in that image correctly.
 In order to solve this problem, the following data was made available to us:
 
   **test_images_mlware.zip** : This contained 5000 images on which we had to gather
   predictions using our OCR model.\
   **train_images_mlware.zip** : This contained the 25000 images with the help of which we
   trained our OCR model.\
   **train-labels_mlware.csv** : This .csv file contained the actual text present in each
   image belonging to the training set.\
   **sample_submission_mlware.csv** : Sample submission

 # Approach

  After exploring several methods, we found TrOCR, an end-to-end text recognition approach
 that employs pre-trained image and text Transformer models, to be a suitable fit for the
 task at hand. TrOCR excels in printed, handwritten, and scene text recognition by
 integrating Transformer architecture for both image understanding and text generation,
 emphasizing simplicity for superior performance. 

 <img src="https://github.com/mbappeenjoyer/OCR_For_Captchas/assets/134948011/bbe85359-d445-471c-b5a2-db1da4e7ae60" width="600" height="400" align="center">\

 <img src="https://github.com/mbappeenjoyer/OCR_For_Captchas/assets/134948011/97414188-2d57-4fdf-97da-cdd077e4d053" width="600" height="400" align="center">


