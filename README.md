
# AI-youtube-summarizer
An AI-powered tool that downloads YouTube videos, transcribes audio using OpenAI Whisper, segments transcripts, and generates detailed, human-like summaries using the Google Gemini API. Ideal for creating timestamped text archives from long videos.

---

# 🎬 YouTube Video Summarizer

[![Python](https://img.shields.io/badge/Python-3.10+-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![YouTube](https://img.shields.io/badge/Platform-YouTube-red)](https://www.youtube.com/)

This project downloads a YouTube video, extracts its audio, transcribes it using **OpenAI Whisper**, segments the transcript, summarizes each chunk using **Google Gemini API**, and produces a detailed timestamped summary report.

---

## 🚀 Features

- **Video Download & Audio Extraction**: Extract MP3 audio from YouTube videos using `yt-dlp`.
- **High-Fidelity Transcription**: Generate timestamped transcripts with Whisper.
- **Segmented Summarization**: Break transcripts into 5-minute chunks for better LLM processing.
- **Abstractive Summaries**: Use Gemini API to generate detailed narrative summaries per chunk.
- **Final Archive**: Produces a comprehensive timestamped text archive of the video content.

---

## 🖼 Pipeline Overview

```

🎥 YouTube Video -> 💾 Download Video (yt-dlp) -> 🎵 Audio Extraction (MP3) -> 📝 Transcription (Whisper) -> ✂️ Transcript Segmentation -> 🤖 Summarization (Gemini API) -> 📄 Final Timestamped Summary

```

---

## 📂 Project Structure

```

youtube-summarizer/
│
├─ Audio to Text.ipynb       # Full Colab notebook with all steps
├─ requirements.txt          # Required Python libraries
├─ README.md
└─ examples/
├─ sample_video_url.txt
└─ sample_summary.txt

````

---

## ⚙️ Installation

Make sure Python 3.10+ is installed. Then install dependencies:

```bash
pip install pytube
pip install git+https://github.com/openai/whisper.git
pip install moviepy
pip install yt-dlp
pip install google-genai
````

---

## 📝 Usage (Colab Notebook)

1. **Set your Gemini API key**:

```python
API_KEY = "<Your Gemini API Key>"
client = genai.Client(api_key=API_KEY)
```

2. **Provide the YouTube video URL**:

```python
youtube_url = "https://www.youtube.com/watch?v=6M5VXKLf4D4"
output_audio_file = "extracted_audio.mp3"
```

3. **Run the notebook**:

* Step 1: Audio extraction from video.
* Step 2: Transcription using Whisper.
* Step 3: Segment transcript into 5-minute chunks.
* Step 4: Summarization using Gemini API.
* Step 5: Combine summaries into a final timestamped archive (`video_summary_archive.txt`).

4. **Download the final archive**:

The notebook automatically downloads the `video_summary_archive.txt` file after processing.

---

## 🖼 Example Output

**Transcript Chunk:**

```
[00:00:05 - 00:02:30] Welcome to our AI tutorial...
```

**Summarized Output:**

```
[00:00:05 - 00:02:30] The video introduces basic AI concepts and the Whisper transcription pipeline. Key points include...
```

---

## ⚡ Notes

* Large videos may take longer due to transcription and summarization.
* Ensure stable internet access for both video downloading and Gemini API calls.
* Timestamps help track key events or topics in the video.

---

