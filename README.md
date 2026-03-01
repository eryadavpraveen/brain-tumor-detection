# 🧠 Brain Tumor Detection API (YOLOv8 + FastAPI)

A production-ready Brain Tumor Detection API built using **YOLOv8**, **FastAPI**, and deployed on **Render**.

This API accepts MRI images and returns tumor detection results using a trained YOLOv8 model.

---

## 📁 Project Structure

```
tumour_yolo_api/
│
├── app/
│   ├── main.py              # FastAPI application entry point
│   ├── yolov8_handler.py    # YOLO model loading & prediction logic
│
├── weights/
│   ├── best.pt              # Trained YOLOv8 model weights
│
├── requirements.txt         # Python dependencies
├── render.yaml              # Render deployment configuration
├── README.md
```

---

## 🚀 Features

- 🧠 Brain tumor detection from MRI images  
- ⚡ YOLOv8 object detection  
- 🌐 REST API using FastAPI  
- 📦 Deployable on Render  
- 📄 Auto-generated Swagger UI  

---

## 🛠 Tech Stack

- Python 3.10+
- FastAPI
- Uvicorn
- Ultralytics YOLOv8
- OpenCV

---

## 📦 Installation (Local Setup)

### 1️⃣ Create Virtual Environment

```bash
python -m venv brain_tumor_env
brain_tumor_env\Scripts\activate   # Windows
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run Locally

From inside `tumour_yolo_api` folder:

```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

Open in browser:

```
http://127.0.0.1:8000/docs
```

You will see interactive Swagger UI.

---

## 📤 API Endpoint

### POST `/predict`

Upload an MRI image to detect tumor.

**Request:**
- Method: POST
- Content-Type: multipart/form-data
- Key: `file`
- Value: Image file (.jpg/.png)

**Example cURL:**

```bash
curl -X POST "http://127.0.0.1:8000/predict" \
  -H "accept: application/json" \
  -H "Content-Type: multipart/form-data" \
  -F "file=@test.jpg"
```

**Sample Response:**

```json
{
  "detections": [
    {
      "class": "tumor",
      "confidence": 0.92,
      "bbox": [120, 85, 300, 260]
    }
  ]
}
```

---

## 🌍 Deployment (Render)

Start Command:

```bash
uvicorn app.main:app --host 0.0.0.0 --port 10000
```

Make sure `requirements.txt` includes:

```
python-multipart
opencv-python-headless
```

After deployment, access:

```
https://your-app-name.onrender.com/docs
```

---

## 🧠 Model Details

- Model: YOLOv8
- Weights: `weights/best.pt`
- Task: Brain Tumor Object Detection
- Input: MRI image
- Output: Bounding box around tumor

---

## ⚠️ Notes

- Model weights are stored in `weights/`
- Large model files may affect deployment performance
- Recommended Python version: 3.10 or 3.11

---

