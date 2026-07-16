# SpongeBob Character Face Matcher

## Project Overview

A browser-based web project that predicts which of eight *SpongeBob SquarePants* characters most closely matches an uploaded face photo.

The image classification model was trained using [Google Teachable Machine](https://teachablemachine.withgoogle.com/). The website loads the trained model through its hosted URL and performs the prediction directly in the browser.

This project was developed in 2023 as part of **Facio**, a high school club, during second year of high school. It was created as an introductory application of image classification and browser-based machine learning.

The project provided introductory experience in:

* collecting and organizing image data,
* defining multiclass image categories,
* training an image classification model,
* publishing a Teachable Machine model,
* processing uploaded files with JavaScript,
* integrating browser-based model inference, and
* presenting classification results through a web interface.

## How It Works

1. The user uploads a face photo by clicking the upload area or dragging and dropping an image.
2. JavaScript reads the selected file and displays a preview.
3. The user clicks the **캐릭터 확인하기** button.
4. The website loads the image classification model from Google Teachable Machine.
5. The model calculates prediction scores for eight character classes.
6. The website selects the class with the highest score.
7. The corresponding character image is displayed as the result.
8. The user can click the **이미지 제거** button to remove the uploaded image and reset the interface.

The result reflects only the visual patterns learned from the original training images. It is not an objective measurement of facial resemblance.

## Character Classes

| Model Label | Character             |
| ----------- | --------------------- |
| `spongebob` | SpongeBob SquarePants |
| `ddung`     | Patrick Star          |
| `squid`     | Squidward Tentacles   |
| `daram`     | Sandy Cheeks          |
| `plankton`  | Sheldon J. Plankton   |
| `puff`      | Mrs. Puff             |
| `Larry`     | Larry the Lobster     |
| `pingping`  | Gary the Snail        |

The original class labels from the training project have been retained, including the capitalization of `Larry`.

## Main Features

* Image upload through a web browser
* Drag-and-drop image input
* Preview of the uploaded image
* Classification across eight character classes
* Selection of the class with the highest prediction score
* Character result image display
* Image removal and interface reset
* Browser-based machine-learning inference
* No backend server or database

## Technologies

* HTML
* CSS
* JavaScript
* Google Teachable Machine
* TensorFlow.js
* Teachable Machine Image library

TensorFlow.js is used through the Teachable Machine Image library.

## Model

The website loads the trained model from the following Teachable Machine model:

```text
https://teachablemachine.withgoogle.com/models/MVRc5pxd6/
```

The model files are not stored in this repository. An internet connection is required to load the model and the external JavaScript libraries.

## Repository Structure

```text
facio-web-project/
├── index.html
├── style.css
└── images/
    ├── title.png
    ├── spongebob.png
    ├── ddung.png
    ├── daram.png
    ├── plankton.png
    ├── pingping.png
    ├── squid.png
    ├── puff.png
    └── larry.png
```

### File Roles

| File or directory  | Purpose                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------- |
| `index.html`       | Defines the interface, image-upload logic, model loading, prediction, and result mapping |
| `style.css`        | Defines the page layout and visual styling                                               |
| `images/title.png` | Default image displayed before prediction and after reset                                |
| `images/*.png`     | Character images displayed according to the predicted class                              |

The files in `images/` are interface assets. They are not part of the model's training dataset and are not used as model inputs.

## Running the Project

### Option 1: Open the HTML file directly

1. Download or clone the repository.
2. Open `index.html` in a web browser.
3. Maintain an internet connection while using the website.

### Option 2: Run a local web server

Clone the repository:

```bash
git clone https://github.com/Seasoning3/facio-web-project.git
cd facio-web-project
```

Start a local server with Python:

```bash
python -m http.server 8000
```

Open the following address:

```text
http://localhost:8000/
```

No npm installation, package manager, or separate machine-learning environment is required.

## Privacy

The selected image is read locally through the browser's `FileReader` API and passed to the model through client-side JavaScript.

The project does not include:

* a backend application,
* a database,
* a server-side image upload function, or
* an image storage system.

The source code does not intentionally save the uploaded image. Photographs should nevertheless be used only with the subject's permission.

## Limitations

* Prediction results depend on the quantity, diversity, and quality of the original training images.
* Lighting, background, pose, dominant colors, and image composition may influence the result.
* Different photographs of the same person may produce different predictions.
* Prediction scores are relative only to the eight classes included in the model.
* The website displays only the highest-scoring character image.
* The original training dataset is not included in the repository.
* The hosted Teachable Machine model must remain publicly accessible.
* An internet connection is required for model inference.
* The model was not scientifically validated.
* The project is not a facial-recognition or psychological assessment system.

## Disclaimer

This project was created solely for educational and entertainment purposes. Its results have no scientific, psychological, or identity-related meaning.

*SpongeBob SquarePants* and its characters are the property of their respective copyright and trademark holders. This independent student project is not affiliated with, endorsed by, or sponsored by Nickelodeon, Paramount, or the official rights holders of *SpongeBob SquarePants*.
