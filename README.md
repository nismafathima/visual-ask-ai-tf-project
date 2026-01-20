
---

# 🚀 VisionAsk AI - TensorFlow Version

**Multimodal Vision-Language System**  
A pure TensorFlow implementation that combines **Object Detection**, **Image Captioning**, **Visual Question Answering (VQA)**, and **Sentiment Analysis** into one pipeline.

---

## ✨ Features
- 🔍 **Object Detection** – EfficientDet-D0 via TensorFlow Hub  
- 📝 **Image Captioning** – InceptionV3 feature extraction + rule-based captions  
- 🤖 **Visual Question Answering (VQA)** – Simple logic-based QA using detection results  
- 💬 **Sentiment Analysis** – Text sentiment classification for captions/questions (Hugging Face Transformers)  
- 🎯 **Complete Analysis Pipeline** – Runs detection, captioning, QA, and statistics in sequence

---

## 📦 Installation
Run the following in **Google Colab** or your local environment:

```bash
pip install tensorflow tensorflow-hub opencv-python-headless
pip install pillow matplotlib numpy requests
pip install transformers
pip install tf-keras
```

---

## 🖼️ Usage

### 1. Load Sample Images
```python
sample_images = load_diverse_images()
```

### 2. Object Detection
```python
detector = TensorFlowObjectDetector()
detections = detector.detect(sample_images['beach'], threshold=0.4)
detector.visualize(sample_images['beach'], detections)
```

### 3. Image Captioning
```python
captioner = TensorFlowImageCaptioner()
caption = captioner.generate_caption(sample_images['food'])
print("Caption:", caption)
```

### 4. Visual Question Answering
```python
vqa = TensorFlowVQA(detector)
answer = vqa.answer_question(sample_images['animals'], "How many animals are there?")
print("Answer:", answer)
```

### 5. Complete Analysis Pipeline
```python
analyze_image_complete(sample_images['city'], 'city')
```

---

## 📊 Example Output
- **Object Detection**: “Found 3 objects: person (92%), car (85%), dog (78%)”  
- **Caption**: “A photo featuring a person, a car, and a dog”  
- **VQA**:  
  - Q: *Is there a person in the image?*  
    A: *Yes, there is a person*  
- **Statistics**: `{ 'person': 2, 'car': 1, 'dog': 1 }`

---

## 🛠️ Project Structure
```
VisionAskAI/
│── visionask_ai.py        # Main pipeline
│── README.md              # Project documentation
│── requirements.txt       # Dependencies
```

---

## 🚀 Future Improvements
- Integrate pretrained captioning models (BLIP, ViT-GPT2)  
- Advanced VQA with multimodal transformers (VisualBERT, LXMERT)  
- Interactive demo using **Gradio** or **Streamlit**  
