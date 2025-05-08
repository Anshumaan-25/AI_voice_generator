# AI Voice Generator 🎙️

A deep learning-based **Voice Conversion Model** built using `so-vits-svc-fork`. This project enables you to convert a source audio's voice into a target speaker's voice using a pretrained or custom-trained model.

## 🚀 Features

✅ Train your own voice conversion model with custom datasets 
✅ Perform inference to convert input audio into your trained voice  
✅ Easy preprocessing pipeline for preparing datasets  
✅ Supports training on Google Colab for GPU acceleration
✅ Code and model checkpoint backup on GitHub

## 🏗️ Project Structure

```
AI_voice_generator/
├── dataset_raw/
├── dataset/44k/
├── logs/44k/
├── pretrained_models/
├── config/
├── src/
├── docs/
├── notebooks/
├── tests/
├── README.md
└── ...
```

## 📦 Installation

1. Clone the repository:

```bash
git clone https://github.com/Anshumaan-25/AI_voice_generator.git
cd AI_voice_generator
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

or manually install:

```bash
pip install torch numpy librosa soundfile pyyaml matplotlib
```

✅ Tested on Google Colab and local Linux system.

## 📝 Usage

### 🔹 **1. Dataset Preparation**
Place your raw audio files inside:

```
/dataset_raw/{speaker_name}/*.wav
```

Run preprocessing:

```bash
python preprocess_flist_config.py
python preprocess_hubert_f0.py
```

### 🔹 **2. Training**
Start training (change params in `config.yaml` if needed):

```bash
python train.py -c configs/config.json -m 44k
```

Training logs and checkpoints will be saved in `/logs/44k/`.

### 🔹 **3. Inference**
To convert a source audio:

```bash
python inference_main.py -m logs/44k/G_*.pth -c configs/config.json -n input.wav -o output.wav
```

## 🎧 Example

| Input Audio | Output Voice (Converted) |
|-------------|--------------------------|
| `input.wav` | `output.wav`             |

Listen to sample outputs in the `/outputs/` folder.

## 📂 Files & Directories

| Folder/File | Description |
|-------------|-------------|
| `/dataset_raw/` | Raw audio input |
| `/dataset/44k/` | Processed dataset (44kHz) |
| `/logs/44k/` | Training checkpoints + logs |
| `/pretrained_models/` | Any pretrained models used |
| `config.json` | Model configuration |
| `README.md` | Project documentation |

## 🙋‍♂️ Author
* **Anshumaan-25**
* GitHub: Anshumaan-25

## ⭐️ Acknowledgements
* so-vits-svc-fork
* OpenAI for model inspiration
* Community contributors

## 📜 License
This project is licensed under the **MIT License**.
