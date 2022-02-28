# YoloV5 Face Mask Detection

# Depencies
Download the yolov5 github repo, move into the main directory and run "pip install -r requirements.txt" to install the necessary libraries.

# Process
1. Download your dataset and split it into three folders: training set, validation set and testing set. Except the testing set folder that will only contain images folder, the two left will contain two differents folders: images and labels. For a custom dataset, you can use online annotation tools to annotate your data.
2. Create the dataset.yaml and set your training and validation images path, label names and their number.
![dataset_yaml_content](https://user-images.githubusercontent.com/48753146/155937201-06473580-0df4-4eb4-9184-aa59d72fd52f.png)
3. Download the yolov5 pretrained model. We have larger, medium and small pretrained weights and you are free to use the one that suits your need. Here, I hav euse the small pretrained model that can be downloaded through this link "wget https://github.com/ultralytics/yolov5/releases/download/v6.0/yolov5s.pt".
4. Launch the training by using the following command: python train.py --img 416 --batch 8 --epochs 50 --data dataset.yaml --weights yolov5s.pt --nosave --cache
5. At the end of your training, the model will specify where you can find the trained model. Mostly saved under "run/train/exp". In the last "exp" folder, you can your current training result.
6. To run the inference. we commonly use the last saved model titled last.pt: python detect.py --source path/to/test/images --weights path/to/your/weights --img 416 --save-txt --save-conf
7. Results from your inference run above can be seen in runs/detect/exp/labels.

# Inference
![result_2](https://user-images.githubusercontent.com/48753146/155939653-d1fca907-19b8-447b-a092-bc996d930eda.png)
![result_3](https://user-images.githubusercontent.com/48753146/155939704-bb40d36e-cce4-4f43-b494-1fc2e2055081.png)
![result_1](https://user-images.githubusercontent.com/48753146/155939729-0665db24-1fa3-43fa-81b2-2340fbc06168.png)


# References
1. yolov5 repo link: https://github.com/ultralytics/yolov5
2. Dataset link: https://www.kaggle.com/deepakat002/face-mask-detection-yolov5
