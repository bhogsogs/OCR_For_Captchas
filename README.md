# Object Character Recognition for Captchas

 OCR (Object Character Recognition) is the technology that enables the conversion of images
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
 <p align="center">
  <img src="https://github.com/mbappeenjoyer/OCR_For_Captchas/assets/134948011/bbe85359-d445-471c-b5a2-db1da4e7ae60" width="600" height="400" align="center">
 </p>

  It was important to first, fine-tune TrOCR so that it could be leveraged for our downstream
 OCR task for Captcha images. For this purpose, we leveraged the pre-trained model
 available on HuggingFace, and implemented a fine-tuning of the pre-trained model by using
 the Seq2Seq trainer. We made use of the Weights and Biases platform to monitor the
 model progress.

 <p align="center">
  <img src="https://github.com/mbappeenjoyer/OCR_For_Captchas/assets/134948011/97414188-2d57-4fdf-97da-cdd077e4d053" width="600" height="400" align="center">
 </p>

 We implemented a 80-20 split between the training and the validation datasets, and defined a PyTorch
 class for the Dataset for easy processing. First, we tried to fine-tune the model with only 3
 epochs(TrOCR_3), which led to a CER loss of 0.02. After this, we fine-tuned our model for a total of 6
 epochs(TrOCR_6), which took 585 minutes (~10 hours) to finish compiling. TrOCR ended up as the best
 performer out of all the approaches that we implemented, achieving a best CER loss of 0.00088 on the
 test image dataset.


  # Results

  We achieved a CER score of 0.00088 on the private(testing) data. 
  (Kaggle Competition [link](https://www.kaggle.com/competitions/mlware24/leaderboard))


