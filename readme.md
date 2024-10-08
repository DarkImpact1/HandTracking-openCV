
<h1>Gesture Volume Control Using OpenCV and MediaPipe</h1>

## Screenshots

<table>
  <tr>
    <td><img src="/images/zero_percent.jpg" alt="Player Input Screen" width="300"/></td>
    <td><img src="/images/twenty_five_percent.jpg" alt="Gameplay Screen" width="300"/></td>
  </tr>
  <tr>
        <td><img src="/images/fifty_percent.jpg" alt="Player Input Screen" width="300"/></td>
    <td><img src="/images/hundered_percent.jpg" alt="Game Over Screen" width="300"/></td>
  </tr>
</table>

### 💾 How to clone this project and run in your local machine

```
git clone https://github.com/DarkImpact1/HandTracking-openCV.git
cd HandTracking-openCV
pip install -r requirements.txt
python main.py
```

### MEDIAPIPE
<div align="center">
  <img alt="mediapipeLogo" src="images/mediapipe_logo.png" />
</div>

> MediaPipe offers open source cross-platform, customizable ML solutions for live and streaming media.

#### Hand Landmark Model
After the palm detection over the whole image our subsequent hand landmark model performs precise keypoint localization of 21 3D hand-knuckle coordinates inside the detected hand regions via regression, that is direct coordinate prediction. The model learns a consistent internal hand pose representation and is robust even to partially visible hands and self-occlusions.

To obtain ground truth data, we have manually annotated ~30K real-world images with 21 3D coordinates, as shown below (we take Z-value from image depth map, if it exists per corresponding coordinate). To better cover the possible hand poses and provide additional supervision on the nature of hand geometry, we also render a high-quality synthetic hand model over various backgrounds and map it to the corresponding 3D coordinates.<br>

<div align="center">
    <img alt="mediapipeLogo" src="images/hand_landmarks_docs.png" height="200 x    " />
</div>
##### Configuration Options
> Naming style and availability may differ slightly across platforms/languages.

+ <b>STATIC_IMAGE_MODE</b><br>
If set to false, the solution treats the input images as a video stream. It will try to detect hands in the first input images, and upon a successful detection further localizes the hand landmarks. In subsequent images, once all max_num_hands hands are detected and the corresponding hand landmarks are localized, it simply tracks those landmarks without invoking another detection until it loses track of any of the hands. This reduces latency and is ideal for processing video frames. If set to true, hand detection runs on every input image, ideal for processing a batch of static, possibly unrelated, images. Default to false.

+ <b>MAX_NUM_HANDS</b><br>
Maximum number of hands to detect. Default to 2.

+ <b>MODEL_COMPLEXITY</b><br>
Complexity of the hand landmark model: 0 or 1. Landmark accuracy as well as inference latency generally go up with the model complexity. Default to 1.

+ <b>MIN_DETECTION_CONFIDENCE</b><br>
Minimum confidence value ([0.0, 1.0]) from the hand detection model for the detection to be considered successful. Default to 0.5.

+ <b>MIN_TRACKING_CONFIDENCE:</b><br>
Minimum confidence value ([0.0, 1.0]) from the landmark-tracking model for the hand landmarks to be considered tracked successfully, or otherwise hand detection will be invoked automatically on the next input image. Setting it to a higher value can increase robustness of the solution, at the expense of a higher latency. Ignored if static_image_mode is true, where hand detection simply runs on every image. Default to 0.5.

<br>

Source: [MediaPipe Hands Solutions](https://google.github.io/mediapipe/solutions/hands#python-solution-api)

<div align="center">
    <img alt="mediapipeLogo" src="images/htm.png" height="360 x" weight ="640 x" />
</div>




<div align = "center">
<h2>📬 Contact</h2>

If you want to contact me, you can reach me through below handles.

<a href="https://twitter.com/dmohit013"><img src="https://upload.wikimedia.org/wikipedia/fr/thumb/c/c8/Twitter_Bird.svg/1200px-Twitter_Bird.svg.png" width="25">@dmohit013</img></a>&nbsp;&nbsp; <a href="https://www.linkedin.com/in/mohit-dwivedi13/"><img src="https://www.felberpr.com/wp-content/uploads/linkedin-logo.png" width="25"> Mohit Dwivedi </img></a>

</div>