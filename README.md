# CuacaVision 🌤️

CuacaVision is a web application that predicts weather conditions based on images of the sky uploaded by the user. It utilizes a deep learning model to classify the weather into one of four categories: stormy (badai), clear (cerah), rainy (hujan), or cloudy (mendung).

## Features

*   **Image-based Weather Prediction:** Upload an image of the sky to get an instant weather forecast.
*   **Clear Predictions:** Displays the predicted weather condition clearly.
*   **Image Preview:** Shows the image you uploaded.
*   **Location-based Information (Frontend):** The application attempts to display your current location and the predicted weather for that area (note: location detection is a browser feature, the prediction is still based on the uploaded image).
*   **Model Insights:** Provides information about the model's accuracy (92%) and the dataset used (>1500 images of Indonesian skies across 4 classes).

## How It Works

1.  The user selects and uploads an image of the sky through the web interface.
2.  The Flask backend receives the image.
3.  The image is preprocessed to fit the input requirements of the deep learning model.
4.  The pre-trained Keras model (`weather_classifier_vgg16.h5`) predicts the weather condition.
5.  The application displays the predicted weather label and the uploaded image to the user.

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```
2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```
3.  **Install dependencies:**
    You'll need Python, Flask, TensorFlow, Keras (usually included with TensorFlow), and NumPy. It's recommended to create a `requirements.txt` file. For now, you can install them manually:
    ```bash
    pip install Flask tensorflow numpy Pillow
    ```
    *(Note: `Pillow` is needed for image manipulation by Keras, `werkzeug` for `img_file.save`)*

4.  **Download/Ensure Model File:**
    Make sure the `weather_classifier_vgg16.h5` file is present in the root directory of the project. If it's stored elsewhere (e.g., via LFS or a download link), provide instructions here.

5.  **Run the application:**
    ```bash
    python app.py
    ```
    The application will typically be available at `http://127.0.0.1:5000/`.

## Usage

1.  Open your web browser and navigate to the application's URL (e.g., `http://127.0.0.1:5000/`).
2.  Click on the "Pilih Gambar Langit" (Choose Sky Image) button to select an image file from your device. You can also use your phone's camera if prompted ("capture='environment'").
3.  Click the "Prediksi Cuaca" (Predict Weather) button.
4.  The predicted weather condition and the uploaded image will be displayed on the page.

## File Structure

```
.
├── app.py                      # Main Flask application file
├── weather_classifier_vgg16.h5 # Pre-trained Keras model
├── static/                     # Directory for static files (images, CSS - though CSS is via CDN here)
│   └── *.webp                  # Example images (not directly used by the app logic but present)
│   └── *.jpeg                  # Example images
├── templates/
│   └── index.html              # HTML template for the web interface
├── .gitignore                  # Specifies intentionally untracked files that Git should ignore
└── README.md                   # This file
```

## Model Details

*   **Model Architecture:** Likely VGG16 (inferred from the filename `weather_classifier_vgg16.h5`).
*   **Classes Predicted:** `badai` (stormy), `cerah` (clear), `hujan` (rainy), `mendung` (cloudy).
*   **Stated Accuracy:** 92% (as displayed on the application's webpage).
*   **Dataset Source:** Trained on over 1,500 images of Indonesian skies.

## Contributing

Contributions are welcome! If you'd like to contribute, please follow these steps:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.

## License

This project is currently unlicensed. You can add an open-source license like MIT if you wish.

## Author

*   **Wahyudi Rayhan Pratama**

(Based on the footer information in `index.html`)
