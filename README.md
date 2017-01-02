# receipt-recognition
Purpose: Predict type of expenses from imaged receipt, using Microsoft's OCR and AzureML. 

Note: 

ML/Data Prep (Python):
----------------------
1. ORC.py contains code for converting unstructured image data into structured text data, which is then used to build a predictive model. The code is then adapted so that it can be hosted within Azure ML's Python Module and make the modelling process self-contained within Azure ML Studio. 

2. This model is trained on ~1100 imaged American receipts for categories: Dining, snack, clothes, feul, groceries, entertainment

3. Web service: https://services.azureml.net/subscriptions/04f7ec88-8e28-41ed-8537-5e17766001f5/resourceGroups/agitare/providers/Microsoft.MachineLearning/webServices/09112016NN6Class.2016.11.9.22.6.12.701


Mobile App (Xamarin):
---------------------
 This is a single page Xamarin Forms based cross platform mobile application which takes an image and calls the partner(Agitare) api to store it in Azure blob storage. Once we get a stored URL to the image, we then pass this URL to Machine learning web service end point to obtain probability scores of different classification groups. The results are shown in a CardViewCell control in a Xamarin forms page. The app uses MVVM pattern to implement this functionality. 

