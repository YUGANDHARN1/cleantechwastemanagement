# Waste Management Classification System

## Overview
An AI-powered waste classification system that uses VGG16 transfer learning to categorize waste materials into four categories: Recyclable, Organic, Hazardous, and Non-Recyclable.

## Features
- Real-time image classification using deep learning
- VGG16 transfer learning model with custom layers
- Responsive web interface with drag-and-drop functionality
- Confidence scores and detailed prediction results
- Professional UI with Bootstrap 5 and custom styling

## Project Structure
```
static/
├── css/
│   └── style.css          # Custom CSS styles
├── js/
│   └── script.js          # JavaScript functionality
└── uploads/               # Image upload directory

templates/
├── index.html             # Main application page
└── portfolio-details.html # Project documentation

flask_app.py              # Main Flask application
vgg16_model.py           # VGG16 model implementation
model.py                 # Original Streamlit model (reference)
data_handler.py          # Data handling utilities
utils.py                 # Helper functions
replit.md                # Project documentation
```

## Technologies Used
- **Backend**: Python 3.11, Flask, TensorFlow/Keras
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **AI/ML**: VGG16 Transfer Learning, Image Processing
- **Libraries**: PIL/Pillow, NumPy, OpenCV

## Installation & Setup

### For VS Code Development:
1. Clone or download the project
2. Install Python 3.11+
3. Install dependencies:
   ```bash
   pip install flask tensorflow pillow numpy opencv-python werkzeug
   ```
4. Run the application:
   ```bash
   python flask_app.py
   ```
5. Open browser to `http://localhost:5000`

### For Replit:
1. The project is pre-configured with all dependencies
2. Use the Flask App workflow to run the application
3. The app will be available on port 5000

## Usage
1. Open the web application
2. Click or drag an image file to the upload area
3. Supported formats: JPG, JPEG, PNG (max 10MB)
4. Click "Classify Waste" to analyze the image
5. View prediction results with confidence scores

## Model Architecture
- **Base Model**: VGG16 pre-trained on ImageNet
- **Custom Layers**: 
  - GlobalAveragePooling2D
  - Dense(512) + Dropout(0.5)
  - Dense(256) + Dropout(0.3)
  - Dense(4, softmax) for classification
- **Input Size**: 224x224x3 RGB images
- **Output**: 4-class probability distribution

## Waste Categories
1. **Recyclable**: Paper, plastic bottles, glass, metal cans
2. **Organic**: Food scraps, garden waste, compostable materials
3. **Hazardous**: Batteries, chemicals, electronics
4. **Non-Recyclable**: Composite materials, certain plastics

## API Endpoints
- `GET /`: Main application page
- `POST /predict`: Image classification endpoint
- `GET /portfolio-details`: Project documentation

## Development Notes
- The model file (`vgg16.h5`) will be created automatically if not present
- Image preprocessing includes resizing, normalization, and RGB conversion
- The web interface provides real-time feedback and error handling
- Responsive design supports both desktop and mobile devices

## Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License
This project is for educational purposes as part of the Smart Internz guided project series.