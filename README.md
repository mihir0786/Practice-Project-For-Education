# 🎤 AI Audio Transcription & Note Generator

An AI-powered bot that transforms audio recordings into structured notes and summaries using state-of-the-art machine learning models.

## ✨ Features

- 🎙️ **Audio Input**: Record live audio or upload files (WAV, MP3, MP4, M4A, FLAC)
- 🗣️ **High-Quality Transcription**: Uses OpenAI Whisper for accurate speech-to-text
- 📝 **AI Summaries**: Generates concise summaries using BART/DistilBART models
- 🎯 **Structured Notes**: Creates topic-wise breakdowns and key points
- 🌍 **Multi-Language Support**: Auto-detection or manual language selection
- 🎨 **Beautiful UI**: Clean, intuitive Gradio interface

## 🚀 Quick Start

### Option 1: Jupyter Notebook (Recommended)

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Launch Jupyter:**
   ```bash
   jupyter notebook audio_transcription_bot.ipynb
   ```

3. **Run all cells** in the notebook to set up the environment and launch the app

### Option 2: Direct Python Execution

1. **Install dependencies:**
   ```bash
   pip install gradio openai-whisper transformers torch torchaudio soundfile librosa numpy pandas
   ```

2. **Run the notebook cells** or extract the Python code to run directly

## 📋 Requirements

- Python 3.8+
- 4GB+ RAM (8GB+ recommended for larger models)
- Internet connection (for initial model downloads)
- Microphone (optional, for live recording)

## 🔧 Customization

### Model Selection
- **Whisper Models**: `tiny`, `base`, `small`, `medium`, `large` (trade-off between speed and accuracy)
- **Summarization Models**: BART, DistilBART, or other HuggingFace models

### Language Support
Currently supports:
- English, Spanish, French, German, Italian
- Portuguese, Russian, Japanese, Chinese
- Auto-detection for unknown languages

## 📊 Model Information

| Component | Model | Size | Speed |
|-----------|--------|------|-------|
| Transcription | Whisper Base | ~140MB | Fast |
| Summarization | BART-Large-CNN | ~1.6GB | Medium |
| Fallback Summary | DistilBART | ~300MB | Fast |

## 🎯 Usage Tips

- **Audio Quality**: Use clear audio with minimal background noise
- **Duration**: Optimal range is 30 seconds to 10 minutes
- **Content Type**: Works best with structured speech (meetings, lectures, presentations)
- **File Formats**: Supports most common audio formats

## 🛠️ Architecture

```
Audio Input → Whisper Transcription → Text Processing → BART Summarization → Structured Notes
     ↓              ↓                      ↓                ↓                    ↓
  Gradio UI    Speech-to-Text       Text Chunking    AI Summary        Topic Extraction
```

## 📝 Output Format

The system generates three types of output:

1. **📝 Transcription**: Raw speech-to-text conversion
2. **📋 Summary**: Concise AI-generated summary
3. **🎯 Structured Notes**: 
   - Key topics mentioned
   - Main points breakdown
   - Timestamp and metadata

## 🚨 Troubleshooting

### Common Issues:

1. **Model Loading Errors**: Ensure sufficient RAM and internet connection
2. **Audio Format Issues**: Convert to supported formats (WAV, MP3, etc.)
3. **Performance Issues**: Use smaller models (`tiny` Whisper, `distilbart`)
4. **Memory Errors**: Reduce audio length or use CPU instead of GPU

### Performance Optimization:

- Use GPU if available: Models automatically detect CUDA
- For CPU-only: Models fall back gracefully
- Chunk long audio files for better processing

## 📄 License

This project uses open-source models and libraries:
- OpenAI Whisper (MIT License)
- HuggingFace Transformers (Apache 2.0)
- Gradio (Apache 2.0)

## 🤝 Contributing

Feel free to submit issues, feature requests, or pull requests to improve this tool!

## 🙏 Acknowledgments

- OpenAI for the Whisper model
- HuggingFace for transformer models
- Gradio team for the excellent UI framework

---

*Built with ❤️ using open-source AI models*