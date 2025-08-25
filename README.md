# 📷 Real-time Image Classifier (Android + TensorFlow Lite)

A real-time **image classification app** built in **Kotlin** using **TensorFlow Lite** and the **Camera2 API**.  
The app streams camera frames, runs them through a TFLite model, and displays predictions instantly — all **on-device** with no internet dependency.

---

## ✨ Features

- 🚀 **Real-time classification** with TensorFlow Lite  
- 📷 **Camera2 API** integration with live preview (`AutoFitTextureView`)  
- 🧠 Plug-and-play support for any `.tflite` classification model  
- 🔁 Image preprocessing utilities (`ImageUtils.kt`)  
- 🧩 Clean separation of **UI**, **Camera**, and **ML** components  
- 💡 On-device inference = **fast** and **private**

---

## 📂 Project Structure

```
app/src/main/java/com/example/realtimeapp/
│── ML/                         # TensorFlow Lite interpreter & helpers
│── AutoFitTextureView.kt       # Resizable TextureView for camera preview
│── CameraConnectionFragment.kt # Handles Camera2 connection & frame callbacks
│── ImageUtils.kt               # Frame conversion (YUV → RGB, resize, normalize)
│── MainActivity.kt             # Entry point & overlay for predictions
```

---

## 🔧 Setup & Installation

### 1. Clone the repo
```bash
git clone https://github.com/<your-username>/Real-time-Image-Classifier.git
```

### 2. Add your TFLite model
- Place your model file as:  
  ```
  app/src/main/assets/model.tflite
  app/src/main/assets/labels.txt
  ```

### 3. Dependencies
In `app/build.gradle`:
```gradle
dependencies {
    implementation 'org.tensorflow:tensorflow-lite:2.14.0'
    implementation 'org.tensorflow:tensorflow-lite-gpu:2.14.0'          // optional
    implementation 'org.tensorflow:tensorflow-lite-select-tf-ops:2.14.0' // optional
}
```

### 4. Run the app
- Open project in **Android Studio**  
- Connect an Android device (API 24+)  
- Run ▶️

---

## ⚙️ How It Works

1. `CameraConnectionFragment` streams frames via Camera2 API  
2. `ImageUtils` preprocesses frames → model input size (e.g., 224×224)  
3. TFLite `Interpreter` runs inference on the frame  
4. Predictions are mapped with `labels.txt` and shown in the UI  

---

## 📸 Demo

*(Add screenshot/gif here of classification running in real-time)*  

---

## 🚀 Future Improvements
- Support multiple models dynamically  
- Add GPU/NNAPI acceleration toggle  
- Overlay bounding boxes for object detection models  

---

## 📝 License
This project is licensed under the MIT License.  
