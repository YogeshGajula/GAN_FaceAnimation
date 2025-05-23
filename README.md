# AI-Driven Facial Animation from Audio

This project enables users to generate animated videos where facial expressions match the spoken content of an audio file. By utilizing **Generative Adversarial Networks (GANs)**, this system animates faces based on the audio input. The project also uses deep learning models to drive these animations, enabling users to sync audio with facial movements in a seamless video.

## Features
- **Generate animated videos** where the facial expressions are synchronized with the audio.
- **Speech-to-text processing** to recognize spoken words and use them as input for the animation.
- **Use of GANs** to generate realistic facial animations based on audio content.

## Installation and Setup

### Prerequisites
Make sure that you have **CUDA** enabled for GPU acceleration in your environment to ensure faster processing of large models and animations. Here’s how to enable it in Google Colab:
- Go to **Edit** → **Notebook settings** → Set **Hardware accelerator** to **GPU**.

### Running the Project in Google Colab

This project is best run on **Google Colab** for faster processing, especially with GPU acceleration. Running it on Colab ensures better computational resources without overloading your local machine. **Colab** provides free access to GPUs, significantly speeding up the training and inference process, especially for tasks requiring high computational power like generating GAN-based animations.

### Steps to Run the Project:

1. **Copy the code from this repo to google colab**:

2. **Run the code  as it prompts**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Install Additional Packages**:
    ```bash
    pip install pydub SpeechRecognition gtts opencv-python-headless ipywidgets
    ```

4. **Mount Google Drive** (for saving the models and outputs):
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```

5. **Download Pre-trained Models**:
    ```bash
    bash scripts/download_models.sh
    ```

6. **Upload Source Image and Audio**:
   Upload your image (face) and audio file (preferably `.wav` format for better processing) via the interface provided.

7. **Run Inference**:
    ```bash
    python3 inference.py --driven_audio <path_to_audio> --source_image <path_to_image> --result_dir <result_directory> --expression_scale 1.5 --preprocess crop
    ```

## Input

The project requires two types of inputs:
- **Source Image**: This should be a clear image of a face (preferably frontal). The image will be used to generate the animated facial expressions.
  - **Format**: `.jpg`, `.png`
- **Driven Audio**: The audio file containing the speech that will drive the animation. The audio is processed for speech-to-text conversion and synchronized with the face's animation.
  - **Format**: `.wav` (for optimal results)

## Output

The output will be a video with a synchronized facial animation based on the input audio. The result is saved as an `.mp4` file.

- **Output Format**: `.mp4`

## Explanation of Results

After running the inference script, the system will generate a video with the facial animation synced to the audio. The key features of the results are:
- The **expression scale** can be adjusted to modify how exaggerated or subtle the facial expressions appear.
- The output video will showcase the source image’s face performing lip-sync and facial movements based on the audio.

Here’s an example of how the generated video looks:
```bash
Result saved at: /path/to/results/generated_video.mp4
```

## Visualization

Here is an example of the animated video generated by the project:

[![Watch the video](https://img.youtube.com/vi/A7tC1bQin10/maxresdefault.jpg)](https://www.youtube.com/watch?v=A7tC1bQin10)



