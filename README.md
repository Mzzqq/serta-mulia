# Serta Mulia

Serta Mulia is a backend application built with Hapi.js that utilizes TensorFlow.js to classify skin conditions from images and stores 
the prediction results in Google Firestore.

## ✨ Features
- Image Classification: Classifies skin images into three categories:
    - Melanocytic nevus 
    - Squamous cell carcinoma 
    - Vascular lesion
- Explanation & Suggestions: Provides medical explanations and suggestions based on the classification result.
- Data Storage: Saves prediction results to Google Firestore.

## 🚀 Technologies
- Node.js
- Hapi.js
- TensorFlow.js
- Google Firestore

## 🔧 Installation
Follow these steps to run the application locally:
1. Clone this repository
```bash
git clone https://github.com/Mzzqq/serta-mulia.git
cd serta-mulia
```
2. Install the dependencies:
```bash
npm install
```
3. Create a .env file in the project root directory and add the following configuration:
```makefile
MODEL_URL='<YOUR_TFJS_MODEL_URL>'
```
4. Start the development server:
```bash
npm run start:dev
```
5. Start the production server:
```bash
npm start
```

## 📋 API Endpoint
POST `/predict`
- Description: Accepts an image file for classification by the model.
- Request:
  - Method: POST 
  - Content-Type: multipart/form-data with the image field
- Response:
  - Status: 201 (Success)
  - Example Response:
```json
{
  "status": "success",
  "message": "Model is predicted successfully.",
  "data": {
    "id": "unique-id",
    "result": "Melanocytic nevus",
    "explanation": "Explanation of the prediction result.",
    "suggestion": "Suggested medical advice.",
    "confidenceScore": 95.5,
    "createdAt": "2024-12-02T00:00:00.000Z"
  }
}
```