<b> run these in a new terminal (mac)</b>
<br><br>
```python3.12 -m venv yolo_env```
<br>```source yolo_env/bin/activate```
<br>```pip install --upgrade pip```
<br>```pip install ultralytics lap```
<br>```python ~/Desktop/unibots-yolo-demo1/yolo-demo.py (or whatever the filepath is for you)```
<br>
<br> ```Dependencies Needed for the localisation code```
<br>```# Install dependencies```
<br>```pip install roboflow ultralytics opencv-python```
<br>```from roboflow import Roboflow```
<br>```rf = Roboflow(api_key="YOUR_API_KEY")```
<br>```project = rf.workspace("YOUR_WORKSPACE").project("YOUR_PROJECT")```
<br>```dataset = project.version(1).download("yolov8")```
<br>
<br> ```from ultralytics import YOLO```
<br>```model = YOLO("yolov8n.pt")  # Start from pretrained nano model```
<br>
<br>```model.train(```
<br>```  data="path/to/dataset/data.yaml",```
<br>```  epochs=100,```
<br>```  imgsz=640,```
<br>```  batch=16,```
<br>```  name="ball_detector",```
<br>```  patience=20,          # Early stopping```
<br>```  augment=True,         # Data augmentation helps with small objects```
<br>```)```

<br>```  # Validate```
<br>```  model.val()```
<br> ``` The data.yaml thing should define classes like ```
<br>```  names:```
<br>```  0: ping_pong_ball```
<br>```  1: ball_bearing```
<br>```  nc: 2```
<br><br><br>
<b>get rid of webcam window with ESC key </b>
