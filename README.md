# EEG Biometrics
This paper presents a novel approach to biometric identification utilising EEG data. The methodology employs a short-time Fourier transform (STFT) for feature extraction, followed by channel-wise division of the data. Subsequently, Convolutional Neural Network (CNN) and Long Short-Term Memory (LSTM) models are implemented individually for each channel. The final step involves the integration of these models using an ensemble voting classifier. Through this ensemble approach, the system shows significant improvements over baseline papers in performance metrics such as accuracy, precision, recall, and f1- score by combining the predictions from multiple models.

## Pre-requisite
- Download the dataset from given urls:
- In root folder of your google drive create a folder named "Major" and upload the datasets into this folder (view the "dataset_path" variable inside the code and arrange the dataset accordingly)

## Dataset
- [Auditory evoked potential EEG-Biometric dataset](https://physionet.org/content/auditory-eeg/1.0.0/)
- [BED: Biometric EEG dataset](https://zenodo.org/records/4309472)

## Setup 
Simply open the ipynb files in google colab and run 

## Code files
### AEP Dataset
- AEP_4_channels: consist of code for simple CNN+LSTM implementation taking all 4 channels at once 
- AEP_attention: consist of code for simple CNN+LSTM with attention model implementation taking all 4 channels at once
- AEP_ensemble: consist of implementation for ensemble learning / voting classifier for the models obtained from AEP_single_channels 
- AEP_single_channels: consist of implementation of indiviual channels. This code has been run each channel with minor changes (change in channel_names)

### BED dataset
- BED_14_channels consist of code for simple CNN+LSTM implementation taking all 14 channels at once 
- BED_14_attention: consist of code for simple CNN+LSTM with attention model implementation taking all 14 channels at once 
- BED_ensemble_4: consist of implementation for ensemble learning / voting classifier for the 4 models (4 selected channels) obtained from BED_single_channels 
- BED_ensemble_14: consist of implementation for ensemble learning / voting classifier for all 14 models obtained from BED_single_channels 
- BED_single_channels: consist of implementation of indiviual channels. This code has been run each channel with minor changes (change in selected column_index)

## Notes:
- The single chanels models are trained and stored in "saved_models" folder which is later loaded in "*_ensemble_*" codes for final voting classification.
