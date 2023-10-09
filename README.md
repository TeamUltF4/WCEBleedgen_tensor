# WCEBleedgen_tensor
## evaluation matrics
![Alt text](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/4e1d59aa-c0a7-4990-bf87-68c7dc6928e4)

</br>image contains the mAP values along with the average precision at various IOU thresholds.


### dataset1 images


![Alt img10](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/576eeff4-6919-42d6-a564-5a2e45c015bf)

</br>image1-:A0010

![Alt img11](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/db5deeaf-bc63-4bb3-80f7-e6a7daf23b9b)

</br>image2-:A0011

![Alt img12](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/e1e8b320-780a-4adc-88c4-5c9a73ff4312)

</br>image3-:A0012

![Alt img33](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/397db6c4-a2fd-44be-81b8-2f81eb101adf)

</br>image4-:A0033

![Alt img40](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/87595088-dc6d-4cd0-9e95-07a89159ab88)

</br>image5-:A0040


## dataset2 images


![Alt 88](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/bdd7112f-dbd1-4088-8ed8-032a352844e1)

</br>image1-:A0088

![Alt 137](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/2f3deaeb-5f45-4372-a498-6bde64e0e5f4)

</br>image2-:A0137

![Alt 146](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/ae3e9883-19c2-4001-8862-8bdc80147ec8)

</br>image3-:A0146

![Alt 148](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/2cddf7e7-be9d-4b23-9bf9-d23f25f979d6)

</br>image4-:A0148

![Alt 447](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/327bc7d8-d21e-4f9a-a29e-e5a547522ac9)

</br>image5-:A0447

![Alt 468](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/7b6c50ac-9017-44fe-97b2-ad5d20cfb594)

</br>image6-:A0468

![Alt 469](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/6ac76c32-b40a-46a7-b14a-d062ef8a6593)

</br>image7-:A0469

![Alt 471](https://github.com/TeamUltF4/WCEBleedgen_tensor/assets/147421232/fad02535-e217-484a-95a8-5b140db9d0d5)

</br>image8-:A0471

### running the model
This guide shows how to set up a TensorFlow Lite Runtime environment on a Windows PC. We'll use [Anaconda](https://www.anaconda.com/) to create a Python environment to install the [TFLite](https://github.com/EdjeElectronics/TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi.git) Runtime in. 

## Step 1. Download and Install Anaconda
First, install [Anaconda](https://www.anaconda.com/), which is a Python environment manager that greatly simplifies Python package management and deployment. Anaconda allows you to create Python virtual environments on your PC without interfering with existing installations of Python. Go to the [Anaconda Downloads page](https://www.anaconda.com/products/distribution) and click the Download button.

When the download finishes, open the downloaded .exe file and step through the installation wizard. Use the default install options.

## Step 2. Set Up Virtual Environment and Directory
Go to the Start Menu, search for "Anaconda Command Prompt", and click it to open up a command terminal. We'll create a folder called `tflite1` directly in the C: drive. (You can use any other folder location you like, just make sure to modify the commands below to use the correct file paths.) Create the folder and move into it by issuing the following commands in the terminal:

```
mkdir C:\tflite1
cd C:\tflite1
```

Next, create a Python 3.9 virtual environment by issuing:

```
conda create --name tflite1-env python=3.9
```

Enter "y" when it asks if you want to proceed. Activate the environment and install the required packages by issuing the commands below. We'll install TensorFlow, OpenCV, and a downgraded version of protobuf. 

```
conda activate tflite1-env
pip install tensorflow opencv-python protobuf==3.20.*
```

copy and paste the TFLite_detection_image.py file present in the repository to C:\tflite1


## Step 3. Move TFLite Model into Directory
Next, take the custom TFLite model that was downloaded from the repository and move it into the C:\tflite1 directory.At this point, you should have a folder at C:\tflite1\custom_model_lite which contains at least a `detect.tflite` and `labelmap.txt` file.

## Step 4. Run TensorFlow Lite Model!
Alright! Now that everything is set up, running the TFLite model is easy. Just call one of the detection scripts and point it at your model folder with the `--modeldir` option. For example, to run your `custom_model_lite` model on a webcam, issue:

```
python  TFLite_detection_image.py --modeldir=custom_model_lite
```

