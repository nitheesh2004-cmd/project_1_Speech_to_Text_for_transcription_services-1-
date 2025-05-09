# project_1_Speech_to_Text_for_transcription_services-1-
🧩 1. Setup & Installation
Installs required packages:

python
Copy
Edit
!pip install kaggle
!pip install transformers torchaudio librosa noisereduce
!pip install openai-whisper
!pip install datasets
📁 2. Data Upload
Prompts user to upload a .tar.gz file (likely a dataset):

python
Copy
Edit
from google.colab import files
files.upload()
🧼 3. Data Cleaning
Loads an audio file (sp01_street_sn5.wav) using librosa

Removes silence and normalizes audio

Plots the cleaned waveform

📊 4. Spectrogram Visualization
Computes a spectrogram of the cleaned audio

Visualizes it using librosa.display.specshow

🧠 5. Feature Extraction
Extracts MFCC (Mel-frequency cepstral coefficients):

python
Copy
Edit
mfcc = librosa.feature.mfcc(y=y_normalized, sr=sr, n_mfcc=13)
Plots the MFCC features.

🗂️ 6. Dataset Handling
Unzips a dataset archive:

python
Copy
Edit
import tarfile
tar = tarfile.open("recordings.tar.gz")
tar.extractall()
tar.close()
📦 7. Load Dataset
Loads dataset metadata using pandas, inspects its structure.

🧪 8. Train-Test Split
Splits the dataset using train_test_split from sklearn.model_selection.

🎙️ 9. Whisper Model (Optional)
Demonstrates how to use OpenAI's Whisper model for transcription:

python
Copy
Edit
import whisper
model = whisper.load_model("base")
result = model.transcribe(audio_path)
print(result["text"])
🧰 10–15. Utility & Analysis Cells
Further code snippets for processing individual audio files

Visualizations and analyses (e.g., class distribution, errors)

📌 16. Final Notes
No explicit summary or final results cell—suggests it may be a work-in-progress or modular code base.

