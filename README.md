# ASR French Model

This repository contains the training notebook of the Automatic Speech Recognition (ASR) model fine-tuned on French audio data. The model aims to provide accurate transcription of French speech into text. This repository includes the fine-tuned model and details for usage, along with example results.

For more information about the model, visit my [Hugging Face Profile](https://huggingface.co/nambn0321/ASR_french_3).

## Model Overview

- Model Name: ASR_french_3

- Task: Automatic Speech Recognition (ASR) for French language

- Architecture: Whisper-small by open AI

- Fine-tuned on: [CV17 dataset](https://huggingface.co/datasets/mozilla-foundation/common_voice_17_0)

## Live Demo

Try the [ASR French Model Demo](https://huggingface.co/spaces/nambn0321/ASR_french) to transcribe French audio samples in real-time.

## Model Performance

- **WER (Word Error Rate):** Measures the percentage of words incorrectly predicted.
- **CER (Character Error Rate):** Measures the percentage of characters incorrectly predicted.

### **Test Set: CV17 (16k samples)**
| Model                      | WER (lower is better)     | CER (lower is better)   |
|----------------------------|---------------------------|-------------------------|
| [**Whisper Small** (baseline)](https://huggingface.co/openai/whisper-small)  | 0.3405    | 0.1680    |
| [**Whisper Medium** (baseline)](https://huggingface.co/openai/whisper-medium) | 0.2597    | 0.1264    |
| **My Model**                  | 0.1648    | 0.0676    |

### **Test Set: MLS (2426 samples)**
| Model                      | WER (lower is better)     | CER (lower is better)   |
|----------------------------|---------------------------|-------------------------|
| [**Whisper Small** (baseline)](https://huggingface.co/openai/whisper-small)  | 0.3271    | 0.1066    |
| **Bofenghuang**              | 0.3020    | 0.1024    |
| [**Whisper Medium** (baseline)](https://huggingface.co/openai/whisper-medium) | 0.2974    | 0.0919    |
| **My Model**                 | 0.3269    | 0.1013    |

## Usage
```python
from transformers import pipeline

# Load the ASR model
asr = pipeline(model="nambn0321/ASR_french_3", task="automatic-speech-recognition")

# Transcribe audio file
audio_file = "path/to/audio.wav"
transcription = asr(audio_file)

print(transcription['text'])
```

## Notes

- Evaluation: The model has been evaluated on a held-out test set, not included in the training data.

- Model Improvements: Ongoing work is focused on improving the transcription accuracy, especially in noisy environments.
