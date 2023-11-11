# Automatic Speaker Recognition using Transfer Learning

## Overview

This project focuses on Automatic Speaker Recognition (ASR) using a custom-made dataset derived from Librivox audiobooks, supplemented with testing data scraped from YouTube or collected live. The dataset encompasses diverse audio samples, varying in speakers' gender, language, and accents. The work involves two datasets: one comprising spectrogram images of audio book segments, and the other with extracted spectral features stored in a table format (.csv) alongside speaker labels.

## Methodology

1. **Dataset Creation:**
   - An intermediate dataset was formed by sampling audio at a rate of 44100Hz in .wav mono format from Librivox audiobooks.
   - Criteria for selecting speakers included uniqueness, a mix of genders and languages, a minimum of 1 hour of audio per speaker, and minimal background noise.
   - The intermediate dataset, consisting of 5-second audio segments from 80 speakers, was then further processed.

2. **CNN Model Architecture:**
   - The CNN model was trained using 19,000 spectrogram images for the training set and 8,200 validation samples for the validation set.

   ![CNN Model Architecture](https://github.com/sonalgan/ASR-TF/assets/57640393/a0a8d1cd-eed5-4c60-b2bd-eeb14d1f22cc)
   *Fig. 2: CNN Model Architecture*

3. **ANN Model Training:**
   - An artificial neural network was trained on the spectral features, including Spectral Centroid, MFCCs, and Spectral Bandwidth.
   - The spectral features were extracted for each audio segment using Librosa and stored in a .csv format with corresponding speaker labels.

4. **Transfer Learning Approach:**
   - Spectrogram images were fed into a network with hidden convolutional layers acting as a feature extractor.
   - The output from both the CNN and ANN models was fed into an SVM classifier for final classification, representing a transfer learning approach.
   - This approach combines the small high performance of SVM with the feature learning capabilities of CNN.

5. **Experiments and Comparison:**
   - After final experiments, the performance of the CNN and ANN models was compared, and the results were discussed.

## Dataset Details

- The intermediate audio dataset was created by breaking down 1-hour samples from 200 speakers into 5-second segments, resulting in approximately 500-700 segments per speaker.
- For the CNN dataset, audio segments were converted into spectrogram images in PNG format, resulting in 19,000 training samples and 8,200 validation samples.
- For the ANN dataset, spectral features were calculated using Librosa and stored in a .csv format, yielding a total of 28,427 samples for 80 speakers.
- Transfer learning data for implementing the models was scraped from YouTube and collected live, featuring 5 speakers with 30s of data each (6 samples) in both spectrogram image and extracted feature formats with corresponding labels.

For a detailed explanation of the project, refer to the published paper: [Link to Published Paper](https://ieeexplore.ieee.org/document/9358539)

## Usage

1. Run `Creating_Datasets.ipynb` to download Librivox audiobooks and create the initial dataset.
2. (Optional) Run `DataProcessing.ipynb` to preprocess files into a zip format before creating datasets.
3. Run `Training_CNN.ipynb` to train the CNN model and store weights.
4. Run `Training_ANN.ipynb` to train the ANN model and store weights.
5. Run `Transfer_Learning.ipynb` to test pretrained models on new data and compare their performance.

## Future Directions

- Explore different model architectures.
- Incorporate more diverse datasets.
- Address any identified limitations.

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

