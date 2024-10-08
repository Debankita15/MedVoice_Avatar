# MedVoice Avatar: Prescription to Speech with AI-Generated Avatars

### Description

**MedVoice Avatar** is an AI-powered application designed to convert medical prescriptions into lifelike speech using text-to-speech (TTS) models like Amazon Polly. This project also integrates with AI-generated avatars, allowing medical information to be presented in an interactive and engaging way. The tool currently supports creating videos where an avatar reads out the prescription text, making medical communication more accessible.

This project is a **work-in-progress** and is part of a **volunteer initiative** aimed at improving patient communication in healthcare settings through cutting-edge AI technologies.

---

### Key Features
- **Text-to-Speech (TTS)**: Converts prescription text into human-like speech using Amazon Polly.
- **Avatar Integration**: Avatars, generated using AI tools such as Artbreeder, are synced with audio output, providing a visual representation.
- **Prescription Processing**: Automatically processes medical prescription data and transforms it into spoken word.
- **Multiple Languages**: Currently supports English with the potential to expand to other languages.

---

### Kaggle Dataset

Using a **Kaggle prescription dataset** for testing purposes in this project. The dataset includes prescription information along with patient problems and the diagnosed disease. You can find the dataset on Kaggle [here](https://www.kaggle.com/datasets/adilmohammed/medical-data?resource=download). This dataset helps test the application’s ability to convert prescription text to speech and synchronize it with the avatar.

For more details on how to integrate the Kaggle dataset:
1. Download the dataset from Kaggle.
2. Mount the Kaggle dataset in Google Colab or your local environment.
3. Use the following command to load the dataset:
   ```python
   import pandas as pd
   df = pd.read_csv('path_to_dataset.csv')
4. Extract the prescription text from the dataset and pass it through the TTS system
   ```python
   prescription_text = df.iloc[0]['Prescription']

---

### Work in Progress
This project is under active development. Here are some of the upcoming features:
- **Character Limit Handling**: Amazon Polly has a limit of 3,000 characters per request. Currently working on strategies to combine audio files for longer prescriptions.
- **Further Avatar Customization**: Aim to improve avatar creation and make it a more seamless part of the pipeline without requiring external uploads.
- **Support for More Languages**: Expanding the TTS service to support more languages.
- **Performance Optimizations**: Currently, generating videos can take a significant amount of time. Working on optimizing this process to reduce the overall runtime.

---

### Weekly Progress

**September 16th - September 22nd**
- **Initial Planning and Dataset Selection**: We explored various datasets and decided to use a Kaggle prescription dataset for our initial testing phase. Preliminary setup of Amazon Polly for TTS was completed, and the basic functionality was tested on sample prescription texts.
- **Avatar Integration Research**: Investigated different avatar creation tools, including Artbreeder, and began integrating these into the project pipeline.
- **TTS Constraints**: Identified the 3,000-character limit of Amazon Polly, and started working on strategies to split the text for longer prescriptions.

**September 23rd - September 29th**
- **Avatar Synchronization and Video Generation**: Successfully integrated Amazon Polly TTS with avatars, generating video output for prescriptions. Initial tests showed that video processing could take up to an hour, so we started optimizing the workflow to reduce time.
- **Character Limit Handling**: Worked on splitting longer texts and combining multiple audio files into a single output.
- **Kaggle Dataset Testing**: Began testing the Kaggle prescription dataset with Amazon Polly and avatar syncing.

---

### Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo/medvoice-avatar.git
   cd medvoice-avatar
   
2. **Install Dependencies**:
   Use the following command to install the required Python libraries.

     ```bash
     pip install -r requirements.txt

3. **Set up Amazon Polly API**:
  To use Amazon Polly for TTS, ensure that you have the necessary access credentials. You can follow Amazon Polly’s setup guide [here](https://docs.aws.amazon.com/polly/).

4. **Run the Application**:
  Use the following command to process a prescription:

     ```bash
     python run.py --prescription_file prescription.txt --avatar avatar_image.jpeg

### How It Works
1. **Scan Prescription**: Upload a medical prescription in text form.
2. **TTS with Amazon Polly**: The text is processed by Amazon Polly, which converts the prescription text into speech.
3. **Avatar**: The user currently uses a default AI-generated avatar.
4. **Video Generation**: The avatar is synchronized with the audio, and a video is generated showing the avatar reading out the prescription.

---

### Challenges
- **Amazon Polly Character Limit**: Amazon Polly has a character limit of 3,000 characters per request. To handle longer texts, we are working on splitting the text into chunks and combining the audio into one output.
- **Video Processing Time**: Video creation can take up to an hour depending on the avatar and audio length. Future updates will optimize this.

---

### To-Do List
- [ ] Improve avatar creation pipeline.
- [ ] Users can upload their custom avatars to personalize the output.
- [ ] Optimize video generation times.
- [ ] Add support for more languages.
- [ ] Handle longer prescriptions by combining smaller audio chunks.
- [ ] Incorporate feedback on avatar customization features.

---

### License
This project is licensed under the MIT License.
