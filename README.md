# Model-Taring---Edge-Impulse
How to Train a ML model on Edge Impulse

You can visit [Link](https://youtu.be/nkENds3GPNs?si=vf1YQZ3EXoSreaMc) for a better and deep understanding

**Steps to Train a Model on Edge Impulse**

#**1. Set up Edge Impulse Studio**
Go to Edge Impulse Studio and log in with your account.

Click Create new project and enter a name for your project. Select the relevant category (e.g., "Image Classification", "Sensor Data", etc.).
![image](https://github.com/user-attachments/assets/3683cdd9-6135-41fb-b855-d79ac3bfa933)



#**2. Collect Data**


**Option 1: Collect Data from Device**

Click on Data Acquisition tab

Connect your device to your computer.

Follow the instructions on Edge Impulse Studio to stream data from the device (e.g., sensors, camera).

Collect enough data to train your model. This could involve recording sensor values, images, or sound samples depending on your project.


**Option 2: Upload Data**
If you already have data collected, you can upload it to Edge Impulse by going to the "Data Acquisition" tab and selecting Upload data. Make sure to label each sample correctly.

![image](https://github.com/user-attachments/assets/e2afa0c8-6dc2-43e4-bed8-94d9e14361d2)


#**3. Label the Data**
After data collection, label the samples appropriately.

For example, in an image classification task, each image should be labeled with the correct class.

For sensor data, create distinct labels for each scenario or condition you're trying to classify.

![image](https://github.com/user-attachments/assets/132ff819-b086-489c-8844-9a2fdf71fdfa)


#**4. Create an Impulse (Model Pipeline)**

Go to the Impulse Design section in Edge Impulse Studio.

Select the type of model you'd like to train. The most common types are:

Classification models: For tasks like object detection or gesture recognition.

Regression models: For tasks like estimating a continuous variable.

Anomaly detection models: For detecting unusual behavior in sensor data.

Add processing blocks (e.g., FFT for audio, image pre-processing) and a learning block (e.g., neural network) based on your project needs.

Configure the model architecture and parameters as necessary.

![image](https://github.com/user-attachments/assets/1d7964b9-f532-474f-b434-8aad545bb71c)




#**5. Configure MFCC Parameters**

Go to "MFCC":

Leave default values or adjust:

Frame length: 0.02s

Frame stride: 0.02s

Filterbanks: 40

Click "Save Parameters"

![image](https://github.com/user-attachments/assets/04f87434-58da-422d-9814-88cf29e9a94b)



#**6. Design the Neural Network**

Go to classifier
- Neural Network (Keras) based model
- then click SAVE & TRAIN

![image](https://github.com/user-attachments/assets/a1036e9f-f987-43a0-afbd-16c4c2d689b1)

After training, check:
- Accuracy
- Loss
- Confusion Matrix

#**7. Model Testing**

Run your Test dataset through the trained model

Analyze:
- Confusion matrix
- Accuracy per class
- Identify overfitting or underperformance

![image](https://github.com/user-attachments/assets/67c4f4c1-0dea-4df8-b7da-f5319f6db505)


#**8. Performance Calibration**

Edge Impulse allows calibration of confidence thresholds

Use this to reduce false positives

E.g., set threshold so model predicts AInak only if >90% confident

![image](https://github.com/user-attachments/assets/8dc3dd4d-0199-4404-9f77-67ca12fa696a)


#**9. Deployment**
Choose:
- Arduino Library (for ESP32)
- C++ Library (for ESP-IDF)

Click Build

Download the library

Integrate in Arduino/ESP-IDF project with your I2S mic input

![image](https://github.com/user-attachments/assets/3b36baab-6d64-42f4-9efd-183b378c6de1)

