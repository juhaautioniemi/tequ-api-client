This repository is developed in Fish-IoT project

https://www.tequ.fi/en/project-bank/fish-iot/ 

---

# tequ-api-client

## Subflows and examples

This repository is collection of useful Node-RED subflows to work with Computer vision and cameras. Repository also contains example subflows to send data to Tequ API. Tequ API is created in Fish-IoT project to receive and archive images and videos and other data. Most of the examples can be used without access to Tequ API.

Tequ API documentation

https://api.tequ.fi/


### Before using subflows related to Computer Vision prepare your machine(s):

- Windows 10: https://github.com/Lapland-UAS-Tequ/win10-nodered-tensorflow

- Jetson Nano/NX: https://github.com/Lapland-UAS-Tequ/tequ-jetson-nodered-tensorflow/

- RPI3/4: https://github.com/Lapland-UAS-Tequ/tequ-rpi-setup

- NVIDIA Triton https://github.com/Lapland-UAS-Tequ/tequ-setup-triton-inference-server

Most of these subflows have external dependencies, that will you need to install before you import flow to Node-RED.

### Available subflows

| Subflow                     | Version         | Desc | JSON |
| ----------------------------|:---------------:| :-------------:| :-------------:|
| [CAM] MPJEG stream          | 0.0.1           | Connect to MPJEG-stream using url. | <a href="subflows/cam-mjpeg.json">json</a> |
| [CAM] RPi HQ MJPEG          | 0.0.1           | Stream MJPEG from RPi HQ-camera (raspistill, raspivid) | <a href="subflows/cam-rpi-hq-camera.json">json</a> |
| [CAM] RPi libcamera         | 0.0.1           | Stream MJPEG from RPi HQ-camera (libcamera) | <a href="subflows/cam-rpi-libcamera-mjpeg.json">json</a> |
| [AI] Detect-sm              | 0.0.1           | Make prediction on image using Tensorflow SavedModel trained with tequ-tf2-ca-training-pipeline | <a href="subflows/ai-detect-sm.json">json</a> |
| [AI] Detect-Triton        | 0.0.1           | Make prediction on image using Tensorflow SavedModel hosted in NVIDIA Triton Inference Server | <a href="subflows/ai-detect-triton.json">json</a> |
| [AI] Detect-acv           | 0.0.1          | Make prediction on image using Tensorflow.js model trained and exported from Microsoft Azure Custom Vision | <a href="subflows/ai-detect-acv.json">json</a>  |
| [AI] Crop & TM           | 0.0.1          | Crops results from '[AI] detect subflows' and classify cropped area(s) using Tensorflow.js model trained and exported from Google Teachable Machine. | <a href="subflows/ai-crop-tm.json">json</a> |
| [IMG] Annotate	            | 0.0.1           | Annotates prediction results from [AI] Inference subflow. | <a href="subflows/img-annotate.json">json</a> |
| [IMG] Thumbnails            | 0.0.1           | Creates thumbnails of original image and annotated image. | <a href="subflows/img-thumbnails.json">json</a> |
| [IMG] Crop detected object(s) | 0.0.1     | Creates thumbnails of original image and annotated image. | <a href="subflows/img-crop-detected-object.json">json</a> |
| [API] Get Token             | 0.0.1           | Retrieve token from Tequ-API. | <a href="subflows/api-get-token.json">json</a> |
| [API] Create datapacket     | 0.0.1           | Creates datapacket ready to send to Tequ-API. Supports Basler BIP2-1920 IP-camera at the moment. | <a href="subflows/api-create-datapacket.json">json</a> |
| [API] Add image            | 0.0.1            | Send image to Tequ-API. Saves image to local filesystem if API is not available. | <a href="subflows/api-add-image.json">json</a> |
| [API] Add video clip       | 0.0.1            | Send image to Tequ-API. Saves image to local filesystem if API is not available. | <a href="subflows/api-add-video.json">json</a> |
| [API] Operation            | 0.0.1            | **N/A** | <a href="subflows/api-operation.json">json</a> |
| Parse JPEG | 0.0.1     | Parse and pre-process JPEG image or image stream | <a href="subflows/Parse%20JPEG.json">json</a> 
| Pre-process [TF]           | 0.0.1            | Pre-process image for Triton Inference Server using tfjs-node-gpu | <a href="subflows/Pre-process [TF].json">json</a> 
| Pre-process                | 0.0.1            | Pre-process image for Triton Inference Server using numjs and piscina | <a href="subflows/Pre-process.json">json</a> | Triton request | 0.0.1     | Send pre-processed image to Triton Inference Server | <a href="subflows/Triton%20request.json">json</a> 
| Post-process | 0.0.1     | Post-process response from Triton request| <a href="subflows/Post%20process.json">json</a> 

### Subflows palette

![alt text](
https://github.com/Lapland-UAS-Tequ/tequ-api-client/blob/master/images/subflows.JPG "Subflows")

### Available example flows

| Flow                      | Version         | Desc           | JSON           |
| --------------------------|:---------------:| :-------------:| :-------------:|
| crop-ca                   | 0.0.1           | Process and crop Cloud Annotations project files. Sort images to folders named by annotation label. | <a href="flows/crop-ca.json">json</a> |
| example-ai-detect-v2      | 0.0.1           | Use [AI] Detect-v2 and [IMG] Annotate | <a href="flows/example-ai-detect-v2.json">json</a> |
| example-ai-detect-sm      | 0.0.1           | Use [AI] Detect-sm and [IMG] Annotate | <a href="flows/example-ai-detect-sm.json">json</a> |
| example-ai-detect-triton  | 0.0.1           | Use [AI] Detect-triton and [IMG] Annotate | <a href="flows/example-ai-detect-triton.json">json</a> |
