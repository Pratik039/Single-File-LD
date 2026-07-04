# 🎙️ Single File Language Diarization System

An end-to-end **Language Diarization** pipeline for processing a **single audio file**. The system performs **Voice Activity Detection (VAD)**, extracts language-related features, and generates language diarization outputs.


## ✨ Features

* 🎤 Voice Activity Detection (Pyannote)
* 🌍 Language Diarization for single audio files
* 📂 Automatic output directory generation
* ⚡ Simple command-line interface
* 🔧 Custom output directory support


## 📦 Requirements

Install the required Python packages before running the system:

pip install kaldi_io
pip install fastcluster
pip install openai-whisper
pip install pyannote.audio==0.0.1

## 🚀 Getting Started

### 1. Extract the Project

Unzip the provided archive:

ld.zip

### 2. Prepare the Audio File

Place the audio file you want to process anywhere on your system and note its full path.


## ▶️ Running Language Diarization

### Default Output Location

Run the following command:

python3 language_diarization.py AUDIO_FILE

**Example**

python3 language_diarization.py /media/MyDataDrive/pratik/single_file_system_LD/B007.wav

The system automatically creates an output directory with the **same name as the input audio file**.

### Custom Output Directory

To save the results in a directory of your choice:

python3 language_diarization.py --output_dir OUTPUT_DIR AUDIO_FILE


**Example**

python3 language_diarization.py --output_dir /media/MyDataDrive/pratik single_file_system_LD/output/media/MyDataDrive/pratik/single_file_system_LD/B007.wav

## 📁 Output

After successful execution, the system generates an output directory containing the language diarization results for the processed audio file.


## 🔑 Hugging Face Authentication

The script `VAD_kaldi_segments.py` uses a **Pyannote Voice Activity Detection (VAD)** model hosted on Hugging Face.

Before running the system:

1. Create a Hugging Face account.
2. Generate an **Access Token** from:

   * **Profile → Settings → Access Tokens → Create New Token**
3. Accept the license agreement for the required Pyannote models on Hugging Face.
4. Replace the token in `VAD_kaldi_segments.py` with your own token (or authenticate using the Hugging Face CLI).

> **Note:** The VAD step will not run unless a valid Hugging Face token is provided.


## 📂 Project Workflow

Input Audio (.wav)
        │
        ▼
Voice Activity Detection (Pyannote)
        │
        ▼
Feature Extraction
        │
        ▼
Language Diarization
        │
        ▼
Output Files



## 🛠️ Troubleshooting

* Ensure all required Python packages are installed.
* Verify that the input audio file exists and the path is correct.
* Make sure your Hugging Face token is valid.
* Accept the license agreements for the required Pyannote models before running the VAD module.
