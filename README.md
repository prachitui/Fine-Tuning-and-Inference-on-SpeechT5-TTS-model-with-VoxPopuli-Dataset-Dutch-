# Fine-Tuning and Inference with SpeechT5 (Text-to-Speech) on Dutch VoxPopuli Dataset

This repository contains a Jupyter notebook for fine-tuning the [SpeechT5](https://arxiv.org/abs/2110.07205) model for Text-to-Speech (TTS) tasks using the Dutch subset of the VoxPopuli dataset. The notebook demonstrates how 
to preprocess the dataset, fine-tune the model on a custom dataset, and perform TTS inference using a locally stored and fine-tuned model and a HiFi-GAN vocoder.

# Overview
## Key Features:
**Dataset:** Preprocessing and cleaning of the VoxPopuli (Dutch) dataset for training the TTS model.
**Model:** Fine-tuning the SpeechT5ForTextToSpeech model with speaker embeddings.
**Vocoder:** Using HiFi-GAN for generating high-quality speech output from text.
**Inference:** Generating Dutch speech from text with the fine-tuned model, stored locally.
The notebook is designed for use in Kaggle environments and assumes the model is stored locally in the Kaggle working directory after fine-tuning.

# Requirements
Install the necessary Python libraries before running the notebook:
```
pip install transformers datasets soundfile speechbrain accelerate matplotlib torch
```
# Usage Instructions
## 1. Fine-Tuning the Model
**Preprocessing:** The notebook loads the VoxPopuli dataset and prepares it by tokenizing the text, resampling the audio to 16kHz, and generating speaker embeddings using SpeechBrain.

**Training:** Fine-tunes the SpeechT5 model on the Dutch dataset using Hugging Face’s Seq2SeqTrainer. Training arguments are set for batch size, learning rate, evaluation steps, and 
other key parameters.


## 2. Running Inference
After training, the fine-tuned model is stored in the local Kaggle working directory and can be used to generate speech from text.

**Inference:** The notebook also shows how to load the locally stored model and use the HiFi-GAN vocoder for generating speech from a given Dutch text. The generated audio is played 
directly in the notebook.

## 3. Audio Output
The generated speech is output as a playable audio object in the notebook using IPython's Audio module. 

[Here](https://github.com/prachitui/Fine-Tuning-and-Inference-on-SpeechT5-TTS-model-with-VoxPopuli-Dataset-Dutch-/blob/main/generated_tts_audio_with_fine_tuned_speect5.wav) is the
generated audio on the fine tuned model.

# Notes
Ensure you have access to the Hugging Face API and models. You can log into Hugging Face using notebook_login() in the notebook.
If using Kaggle, save/upload your fine-tuned model to the working directory for inference.
Modify the input text for TTS to generate speech for your custom sentences.
