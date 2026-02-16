# VideoLingo Kazakh

A fork of [VideoLingo](https://github.com/Huanshere/VideoLingo) with modifications and enhancements for Kazakh language support. This all-in-one video translation, localization, and dubbing tool generates Netflix-quality subtitles and high-quality dubbing.

## About This Fork

This is a modified version of the original VideoLingo project, adapted to support Kazakh language translation and dubbing. All modifications maintain compatibility with the original codebase while adding specific features for Kazakh language processing.

## Features

- **Video Translation**: YouTube video download and processing via yt-dlp
- **Word-level Subtitle Recognition**: Low-illusion subtitle recognition with WhisperX
- **NLP and AI-powered Segmentation**: Smart subtitle segmentation
- **Custom Terminology**: AI-generated terminology for coherent translation
- **3-step Translation Process**: Translate-Reflect-Adaptation for cinematic quality
- **Netflix-standard Subtitles**: Single-line subtitles only
- **Multiple TTS Options**: GPT-SoVITS, Azure, OpenAI, Edge TTS, and more
- **Kazakh Language Support**: Enhanced support for Kazakh language translation and dubbing
- **Streamlit Interface**: One-click startup and processing
- **Multi-language UI**: Support for multiple languages in the interface
- **Detailed Logging**: Progress tracking with resume capability

## Key Differences from Original

This fork includes:
- Enhanced Kazakh language translation capabilities
- Optimized TTS settings for Kazakh voices
- Custom configuration for Kazakh language processing
- Additional documentation for Kazakh language users

## Installation

### Prerequisites

- Python 3.10
- ffmpeg installed on your system

**Windows with NVIDIA GPU:**
1. Install [CUDA Toolkit 12.6](https://developer.download.nvidia.com/compute/cuda/12.6.0/local_installers/cuda_12.6.0_560.76_windows.exe)
2. Install [CUDNN 9.3.0](https://developer.download.nvidia.com/compute/cudnn/9.3.0/local_installers/cudnn_9.3.0_windows.exe)
3. Add `C:\Program Files\NVIDIA\CUDNN\v9.3\bin\12.6` to your system PATH
4. Restart your computer

**Install FFmpeg:**
```bash
# Windows (using Chocolatey)
choco install ffmpeg

# macOS (using Homebrew)
brew install ffmpeg

# Linux (Debian/Ubuntu)
sudo apt install ffmpeg
```

### Installation Steps

1. Clone the repository:
```bash
git clone https://github.com/stukenov/video-lingo-kazakh.git
cd video-lingo-kazakh
```

2. Install dependencies (requires Python 3.10):
```bash
conda create -n videolingo python=3.10.0 -y
conda activate videolingo
python install.py
```

3. Configure the application:
```bash
cp config.yaml.example config.yaml
# Edit config.yaml with your API keys and settings
```

4. Start the application:
```bash
streamlit run st.py
```

### Docker (Alternative)

Requires CUDA 12.4 and NVIDIA Driver version >550:
```bash
docker build -t videolingo-kazakh .
docker run -d -p 8501:8501 --gpus all videolingo-kazakh
```

## Configuration

Edit `config.yaml` to configure:

### API Settings
- LLM: `claude-3-5-sonnet`, `gpt-4.1`, `deepseek-v3`, `gemini-2.0-flash`, etc.
- WhisperX: Run locally or use 302.ai API
- TTS: `azure-tts`, `openai-tts`, `edge-tts`, `GPT-SoVITS`, etc.

### Language Settings
- Set `target_language` to 'Kazakh' or other target language
- Configure source language in whisper settings

### TTS Settings for Kazakh
For Kazakh language dubbing, use Edge TTS with Kazakh voices:
```yaml
tts_method: 'edge_tts'
edge_tts:
  voice: 'kk-KZ-AigulNeural'  # or 'kk-KZ-DauletNeural'
```

## Usage

1. Start the Streamlit interface:
```bash
streamlit run st.py
```

2. Upload your video or provide a YouTube URL

3. Configure translation settings:
   - Select source language
   - Set target language (Kazakh)
   - Choose TTS method

4. Click "Start Processing" and wait for completion

5. Download the processed video with translated subtitles and dubbing

## API Services

This project works with various API services:
- **[302.ai](https://gpt302.saaslink.net/C2oHR9)**: One API key for all services (LLM, WhisperX, TTS)
- **Local Options**: Run with Ollama and Edge-TTS for free, no API needed

## Project Structure

```
video-lingo-kazakh/
├── core/                    # Core processing modules
├── translations/            # UI translations
├── docs/                    # Documentation
├── st.py                   # Streamlit application
├── install.py              # Installation script
├── config.yaml.example     # Example configuration
└── requirements.txt        # Python dependencies
```

## Known Limitations

1. WhisperX transcription may be affected by background noise
2. Weaker LLM models can cause JSON format errors
3. Dubbing may not be 100% perfect due to language differences
4. Multilingual video transcription retains main language only
5. Cannot dub multiple characters separately yet

## Kazakh Language Notes

When using this fork for Kazakh language:
- Ensure proper Kazakh voice selection in TTS settings
- Use appropriate Kazakh language models
- Consider using Edge TTS with native Kazakh voices for best results

## License

MIT License - see [LICENSE](LICENSE) file for details

Copyright (c) 2025 Saken Tukenov

This project is based on [VideoLingo](https://github.com/Huanshere/VideoLingo) by Huanshere, licensed under Apache 2.0.

## Acknowledgments

### Original Project
- [VideoLingo](https://github.com/Huanshere/VideoLingo) by Huanshere

### Dependencies
- [whisperX](https://github.com/m-bain/whisperX) - Speech recognition
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) - YouTube video download
- [json_repair](https://github.com/mangiucugna/json_repair) - JSON repair
- [BELLE](https://github.com/LianjiaTech/BELLE) - Language models

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

For issues related to Kazakh language support, please open an issue on GitHub.

For the original VideoLingo project:
- GitHub: [@Huanshere](https://github.com/Huanshere)
- Twitter: [@Huanshere](https://twitter.com/Huanshere)
- Email: team@videolingo.io

---

If you find this fork helpful, please give it a star!
