<h1>Deep Learning Traffic Jam Analysis</h1>
<p>This project applies <strong>Deep Learning</strong> and <strong>Transfer Learning</strong> techniques to analyze real-time traffic. It integrates advanced architectures such as <strong>YOLOv8</strong>, <strong>U-Net</strong>, and <strong>ResNet50</strong> to detect vehicles, segment roads, and predict traffic congestion.</p>
<h2>🚀 Features</h2>
<ul>
      <li><strong>Vehicle detection</strong> using YOLOv8</li>
      <li><strong>Road segmentation</strong> using U-Net based on ResNet50</li>
      <li><strong>Traffic congestion prediction</strong> using ResNet50</li>
      <li><strong>Visualization of results</strong> with bounding boxes and segmentation masks</li>
</ul>
    
<h2>📌 Prerequisites</h2>
<p>Install the required libraries:</p>
<pre><code>pip install ultralytics roboflow torch torchvision matplotlib segmentation-models-pytorch albumentations opencv-python</code></pre>
<h2>📂 Dataset Structure</h2>
<ul>
      <li><code>train/images/</code>: Training images</li>
      <li><code>valid/images/</code>: Validation images</li>
      <li><code>data.yaml</code>: Configuration file</li>
</ul>
<h2>🔍 Vehicle Detection with YOLOv8</h2>
<pre><code>yolo_model.train(data="data.yaml", epochs=5, imgsz=640, batch=32, name="vehicle_detection", pretrained=True)</code></pre>
<h2>🖼️ Visualization of Results</h2>
<pre><code>is_jam, vehicle_count = process_image('/path/to/image.jpg', resnet_model, unet_model, yolo_model)
print(f"Traffic Jam Detected: {is_jam}, Vehicle Count: {vehicle_count}")</code></pre>
<h2>📊 Testing on a Full Dataset</h2>
<pre>
  <code>
    resnet_model = load_resnet_model()
    unet_model = load_unet_model()
    resultas="/content/drive/MyDrive/results.txt"
    test_on_dataset('/content/drive/MyDrive/vehicle_detection_yolov8/valid/images', resnet_model, unet_model, yolo_model, "/content/drive/MyDrive/results.txt")
  </code></pre>
<h2>📈 Results</h2>
<ul>
    <li>Analyzed images: <strong>90</strong></li>
    <li>Detected traffic jams: <strong>73</strong></li>
    <li>Report saved in: <code>/content/drive/MyDrive/results.txt</code></li>
</ul>
    
<h2>🤝 Contributions</h2>
<p>Contributions are welcome! Fork the repository and submit a pull request.</p>
    
<h2>💡 Future Improvements</h2>
<ul>
    <li>Integration of a real-time prediction module</li>
    <li>Optimization with Swin Transformer</li>
</ul>
