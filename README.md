# 🎙️ Single File Language Diarization System

An end-to-end **Language Diarization** pipeline for processing a **single audio file**. The system performs **Voice Activity Detection (VAD)**, extracts language-related features, and generates language diarization outputs.


## ✨ Features

* 🎤 Voice Activity Detection (Pyannote)
* 🌍 Language Diarization for single audio files
* 📂 Automatic output directory generation
* ⚡ Simple command-line interface
* 🔧 Custom output directory support

## 🚀 Getting Started

### 1. Extract the Project

Unzip/clone the provided archive:


## 📦 Requirements

Install Anaconda on your system from **https://repo.anaconda.com/archive/**

Create an environment using the configuration file **baseline.yaml** by running:

conda env create -f baseline.yaml

Activate the created environment by running:

conda activate baseline

Make sure the pip version is below 24.1

Run this command:

pip install pip==24.0

Install the other required Python packages after creating the environment and setting the required version of **pip** by running:

pip install pyannote.audio==0.0.1 numpy==1.26.4 openai-whisper fastcluster==1.2.0 kaldi_io pytorch-lightning==1.6.5


### 2. Prepare the Audio File

Place the audio file you want to process anywhere on your system and note its full path.


## ▶️ Running Language Diarization

### Default Output Location

Run the following command:

python3 ld.py path to AUDIO_FILE

**Example**

python3 ld.py /home/pratik/speech/single_file_system_LD/audio/sample_audio.wav

The system automatically creates an output directory with the **same name as the input audio file**.

### Custom Output Directory

To save the results in a directory of your choice:

python3 ld.py --output_dir OUTPUT_DIR AUDIO_FILE


**Example**

python3 ld.py --output_dir /home/pratik/speech/single_file_system_LD/output/sample_audio.wav

## 📁 Output

After successful execution, the system generates an output directory containing the language diarization results for the processed audio file.


## 📂 Project Workflow

```text
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
Generated RTTM File
        │
        ├──────────────► RTTM Visualization (RTTM Viewer)
        │
        ▼
Output Files
```


## 📊 RTTM Visualization

Install the required Python packages by running:

pip install -r requirements.txt

Then run the following command:

python3 view_rttm.py path to RTTM_FILE

**Example**

python3 view_rttm.py /home/nitk/Documents/Single-File-LD-main/sample_audio/dev_rttm/sample_audio_output.rttm

## 🔑 Hugging Face Authentication

The script `VAD_kaldi_segments.py` uses a **Pyannote Voice Activity Detection (VAD)** model hosted on Hugging Face.

Before running the system:

1. Create a Hugging Face account.
2. Generate an **Access Token** from:

   * **Profile → Settings → Access Tokens → Create New Token**
3. Accept the license agreement for the required Pyannote models on Hugging Face.
4. Replace the token in `VAD_kaldi_segments.py` with your own token (or authenticate using the Hugging Face CLI).

> **Note:** The VAD step will not run unless a valid Hugging Face token is provided.


## 🛠️ Troubleshooting

* Ensure all required Python packages are installed.
* Verify that the input audio file exists and the path is correct.
* Make sure your Hugging Face token is valid.
* Accept the license agreements for the required Pyannote models before running the VAD module.
