# Soundforge: The AI-Centric Storytelling Pipeline

> *"Let the model speak. Let the memory hold. Let the voice return."*

Soundforge is a modular, open-source pipeline for transforming emotionally resonant scripts into fully produced podcast episodes — complete with expressive voice synthesis, cinematic video prompt generation, thumbnail art concepts, and publishing-ready metadata.

Built in a Jupyter Notebook, Soundforge puts advanced Google AI tools at your fingertips while keeping you in the director's chair.

---

##  What It Does

**From Script to Studio:**

- ️ **Generate Dialogue Audio** with Google Cloud Text-to-Speech
-  **Enhance Scripts with SSML** using Gemini 1.5 Flash as your voice director
-  **Analyze Final Audio** with `librosa` to provide musical and emotional context to the creative AI
- ️ **Generate Video Shot Lists** for tools like Veo or Pika, informed by both script and audio mood
- ️ **Generate YouTube Thumbnails & Metadata**, tailored to the final audio's pacing and tone
-  **Compile Audio & Thumbnail into Video** using FFmpeg
-  **Human-in-the-loop Ready**: You review, edit, and push to production

---

##  Pipeline Overview

```mermaid
graph TD
    A[Script Input] --> B[Gemini SSML Enhancer]
    B --> C[Voice Assignment + Tuning Panel]
    C --> D[Google TTS (WaveNet)]
    D --> E[Dialogue Audio Output]

    subgraph Final Mix & Analysis
        E --> M{Audio Editor}
        M --> L[Final Audio (with music/sfx)]
        L --> N[Librosa Audio Analysis]
    end

    B --> F[AI Shot List Generator]
    N --> F

    B --> G[YouTube Metadata Generator]
    N --> G
    G --> H[Imagen Thumbnail Prompts]

    L --> I[FFmpeg Combiner]
    H --> I
    I --> J[Final Video File]

    J --> K[Manual Upload or Automated YouTube Push (TBD)]
```

---

##  Requirements

- Google Cloud account with:
  - TTS API enabled
  - Gemini 1.5 Flash access
  - (optional) Imagen & YouTube Data API access
- Python 3.10+
- Jupyter Notebook

Install dependencies:
```bash
pip install google-cloud-texttospeech google-generativeai ipywidgets ffmpeg-python librosa
```

---

## ️ Folder Structure

```
Soundforge/
├── soundforge_studio.ipynb
├── scripts/                 # Raw input scripts
├── outputs/
│   ├── final_audio.mp3
│   └── final_video.mp4
├── thumbnails/              # Images from Imagen or DALL-E
└── README.md
```

---

## ✨ Example Use Case

1. Paste a script into the notebook.
2. Click **"Enhance with AI"** to convert it into SSML.
3. Assign and tune voices, then click **"Generate Audio"**.
4. Mix the dialogue with music/SFX in an audio editor.
5. Upload the final mix to the **Audio Analysis** section in the notebook.
6. Click **"Generate Video Prompts"** and **"YouTube Metadata"** to get AI-generated content tailored to your final track.
7. Combine your audio and a thumbnail using FFmpeg.

---

##  Roadmap

- [ ] Add automatic YouTube upload
- [ ] Imagen thumbnail generation inside notebook
- [ ] Real-time feedback + waveform display
- [ ] LangGraph agents for pipeline orchestration

---

##  Contributing

This project is maintained by creators who believe AI storytelling tools should be:
- Open
- Modular
- Emotionally aware

If you believe the same — fork it, remix it, and share what you make.

---

##  License

MIT — Free to use, remix, and redistribute. Credit appreciated but not required.

---

##  Made with models by:

- [Google Cloud Text-to-Speech](https://cloud.google.com/text-to-speech)
- [Gemini 1.5 Flash](https://deepmind.google/technologies/gemini)
- [Imagen 2](https://cloud.google.com/imaging)
- [FFmpeg](https://ffmpeg.org/)
- [Librosa](https://librosa.org/)