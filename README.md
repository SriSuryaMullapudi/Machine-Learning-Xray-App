# Machine-Learning-Xray-App


Here are the steps to test with your own CXR images (click on the "View all of README.md"):

Download and install Microsoft Office Lens here.
Display a CXR image on your screen (PACS system or PC).
Open Microsoft Office Lens and take a snapshot of the CXR image under the "DOCUMENT" mode (adjust border if needed).
Choose the "GRAYSCALE" filter and save the snapshot.
Open our App, load the snapshot from the gallery and make the prediction (check the following live demo).

Pre-training Data (108,948 CXR Images)
ChestX-ray8: Hospital-scale Chest X-ray Database and Benchmarks on Weakly-Supervised Classification and Localization of Common Thorax Diseases.
Fine-tuning Data (537 CXR Images)
COVID-19 Image Data Collection.
RSNA Pneumonia Detection Challenge.
Fine-tuning data is split into training/validation/testing sets with 125/18/36 images for each class.
Follow-up Dataset


Model Training and Evaluation

Codes and learned model parameters are available in the Main folder. Here are the steps for training and testing:

Triage Model:

Put the CXR images in the Dataset folder as the following structure:
Dataset
   train
      clean
      covid
      pneumonia
   test
      clean
      covid
      pneumonia
   validation
      clean
      covid
      pneumonia
Download the pre-trained model here and save it into RF_model folder.
Run the .ipynb file for triage model training and testing.
Follow-up Model:

Put the COVID-19 CXR images and metadata.csv from COVID-19 Image Data Collection in the Dataset_FollowUp folder.
Run the code of severity scoring system to assign opacity scores to CXR images and save them to metadata.csv.
Run the feature.ipynb to extract and save features from CXR images.
Run the data_generation.ipynb to generate CXR image sequences and assign corresponding radiological trajectory labels.
Run the model_FollowUp.ipynb for follow-up model training and testing.


We provide the source code for deployment with Pytorch Mobile and Android Studio, which is developed based on this repository. The source code contains an example model, if you want to deploy other models, here are the steps:

Download the pre-trained models.
Use the script "TorchScript_converter.py" to convert the model to TorchScript (.pt).
Put the model under "src/main/assets" folder
Change the path in 'MainActivity.java' to the current .pt file.
Build and test.




