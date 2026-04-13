<div align="center">

<!-- Animated Header -->
<!-- Capsule Render Banner (very reliable) -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:4285F4,100:34A853&height=200&section=header&text=Gemini%20AI%20Learner&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Learn%20Google%20Gemini%20AI%20Step%20by%20Step&descAlignY=58&descSize=20" width="100%"/>

<br/>

<!-- Typing SVG — no emojis, clean URL -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=24&pause=1000&color=4285F4&center=true&vCenter=true&width=700&lines=Learn+Google+GenAI+Step+by+Step;Text+Generation+%7C+Image+%7C+Video;Build+Real+AI+Projects+with+Python;From+Zero+to+AI+Hero" alt="Typing SVG" />

<br/>

<!-- Repo Description -->
<p align="center">
  <b>A beginner-to-advanced learning notebook for <a href="https://ai.google.dev/">Google Gemini AI</a> — structured lessons covering text generation, image understanding, AI assistants, image creation, and video generation. Learn by doing.</b>
</p>

<br/>

<!-- Badges Row 1 -->
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Google Gemini](https://img.shields.io/badge/Google-Gemini_AI-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)

<!-- Badges Row 2 -->
[![google-genai](https://img.shields.io/badge/google--genai-Latest-orange?style=for-the-badge&logo=google&logoColor=white)](https://pypi.org/project/google-genai/)
[![python-dotenv](https://img.shields.io/badge/python--dotenv-Configured-yellow?style=for-the-badge&logo=dotenv&logoColor=white)](https://pypi.org/project/python-dotenv/)
[![Pillow](https://img.shields.io/badge/Pillow-Image_Processing-blueviolet?style=for-the-badge&logo=python&logoColor=white)](https://pillow.readthedocs.io/)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge&logo=statuspage&logoColor=white)]()

<br/>

<!-- Divider -->
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

</div>

---

## 📋 Table of Contents

- [✨ Features](#-features)
- [🗂️ Project Structure](#-project-structure)
- [🚀 Getting Started](#-getting-started)
- [🔑 API Key Setup](#-api-key-setup)
- [📓 Notebook Walkthrough](#-notebook-walkthrough)
- [🧠 Models Used](#-models-used)
- [📦 Requirements](#-requirements)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

---

## ✨ Features

<div align="center">

| 🚀 Feature | 📝 Description | 🤖 Model |
|---|---|---|
| **Content Generation** | Generate structured text like AI/ML roadmaps | `gemini-3-flash-preview` |
| **Thinking Mode** | Controlled reasoning with configurable thinking levels | `gemini-3-flash-preview` |
| **System Instructions** | Custom AI personas (e.g. Python Tutor) with temperature control | `gemini-3-flash-preview` |
| **Image Understanding** | Analyze real-world images and extract meaningful info | `gemini-3-flash-preview` |
| **AI Personal Assistant** | Q&A bot + Email Summarizer with OOP design | `gemini-2.5-flash` |
| **Image Generation** | Create photorealistic images from text prompts | `gemini-3.1-flash-image-preview` |
| **Image Editing** | Edit existing images using natural language prompts | `gemini-3.1-flash-image-preview` |
| **Text-to-Video** | Generate cinematic video clips from descriptive prompts | `veo-3.1-generate-preview` |

</div>

---

## 🗂️ Project Structure

```
gemini-ai-learner/
│
├── 📓 code.ipynb              # Main Jupyter Notebook with all experiments
├── 🔐 .env                    # Environment variables (API key — never commit this!)
├── 🖼️ generated_image.png     # Output from image generation cell
├── 🎬 dialogue_example.mp4    # Output from text-to-video cell
└── 📄 README.md               # You are here!
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/saifullah857/gemini-ai-learner
cd gemini-ai-learner
```

### 2. Create a Virtual Environment *(Recommended)*

```bash
conda create -n gemini_env python=3.10
conda activate gemini_env
```

> Or using venv:
> ```bash
> python -m venv venv
> source venv/bin/activate  # Windows: venv\Scripts\activate
> ```

### 3. Install Dependencies

```bash
pip install -q -U google-genai
pip install python-dotenv pillow requests
```

### 4. Configure Your API Key

```bash
# Create a .env file in the project root
echo GEMINI_API_KEY="your_api_key_here" > .env
```

### 5. Launch the Notebook

```bash
jupyter notebook code.ipynb
```

---

## 🔑 API Key Setup

1. Visit **[Google AI Studio](https://aistudio.google.com/app/apikey)**
2. Sign in with your Google Account
3. Click **"Create API key"**
4. Copy the key and paste it into your `.env` file:

```env
GEMINI_API_KEY="your_actual_api_key_here"
```

> ⚠️ **Security Warning:** Never push your `.env` file to GitHub. Add it to `.gitignore`:
> ```bash
> echo ".env" >> .gitignore
> ```

The notebook loads the key securely using `python-dotenv`:

```python
from dotenv import load_dotenv
import os

load_dotenv()
api_key = os.getenv("GEMINI_API_KEY")
```

---

## 📓 Notebook Walkthrough

### 🔹 Section 1 — Basic Content Generation

Uses the Gemini API to generate a full, structured **AI/ML Engineer Roadmap** broken into 7 phases — from Math & Python foundations all the way to MLOps and portfolio building.

```python
response = client.models.generate_content(
    model="gemini-3-flash-preview",
    contents="Road map of AI / ML in built point"
)
print(response.text)
```

---

### 🔹 Section 2 — Thinking with Gemini

Configures Gemini's **ThinkingConfig** to control the reasoning depth before generating a response.

```python
config = types.GenerateContentConfig(
    thinking_config=types.ThinkingConfig(thinking_level="low")
)
```

---

### 🔹 Section 3 — System Instructions

Creates a **Python Tutor AI** with system-level instructions, giving Gemini a specific persona and controlling output creativity via temperature.

```python
config = types.GenerateContentConfig(
    system_instruction="You are an expert Python tutor. Always explain step by step.",
    temperature=0.2
)
```

---

### 🔹 Section 4 — Image Understanding

Feeds a real image (Pakistan flag via URL) to Gemini and asks for country info, capital, leadership, and cultural facts.

```python
image = Image.open(BytesIO(requests.get(image_url).content))
response = client.models.generate_content(
    model="gemini-3-flash-preview",
    contents=[image, "Tell me about this country..."]
)
```

---

### 🔹 Section 5 — AI Personal Assistant

A Python **OOP-based** assistant class with two capabilities:
- `ans_query()` — answers any question interactively
- `summarize_email()` — summarizes pasted email content in 2–3 sentences

```python
class PersonalAssistant:
    def ans_query(self): ...
    def summarize_email(self): ...

assistant = PersonalAssistant()
assistant.ans_query()
```

---

### 🔹 Section 6 — Image Generation

Generates a **photorealistic image** from a creative text prompt using Gemini's image model.

```python
prompt = "A person playing cricket on the moon with a friend, realistic style"
response = client.models.generate_content(
    model="gemini-3.1-flash-image-preview",
    contents=[prompt]
)
image.save("generated_image.png")
```

---

### 🔹 Section 7 — Image Editing

Edits an **existing image** using a natural language prompt — placing your cat in a fancy restaurant under the Gemini constellation.

---

### 🔹 Section 8 — Text-to-Video Generation

Generates a **short cinematic video** from a detailed scene description using the Veo model, with async polling until completion.

```python
operation = client.models.generate_videos(
    model="veo-3.1-generate-preview",
    prompt=scene_description
)
while not operation.done:
    time.sleep(10)
    operation = client.operations.get(operation)

generated_video.video.save("dialogue_example.mp4")
```

---

## 🧠 Models Used

<div align="center">

| Model | Capability |
|---|---|
| `gemini-3-flash-preview` | Fast text generation, reasoning, image understanding |
| `gemini-2.5-flash` | Personal assistant tasks, summarization |
| `gemini-3.1-flash-image-preview` | Text-to-image & image editing |
| `veo-3.1-generate-preview` | Text-to-video generation |

</div>

---

## 📦 Requirements

```txt
google-genai>=1.0.0
python-dotenv>=1.0.0
Pillow>=10.0.0
requests>=2.28.0
```

Install all at once:

```bash
pip install google-genai python-dotenv Pillow requests
```

**Python Version:** `3.10+`
**Notebook Environment:** Jupyter Notebook / JupyterLab / VS Code

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to your branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1000&color=4285F4&center=true&vCenter=true&width=500&lines=Built+with+love+using+Google+Gemini+AI;Happy+Learning!" alt="Footer" />

<br/>

[![Made with Python](https://img.shields.io/badge/Made%20with-Python-1f425f?style=flat-square&logo=python)](https://python.org)
[![Powered by Gemini](https://img.shields.io/badge/Powered%20by-Google%20Gemini-4285F4?style=flat-square&logo=google)](https://ai.google.dev)
[![Open in Jupyter](https://img.shields.io/badge/Open%20in-Jupyter-F37626?style=flat-square&logo=jupyter)](https://jupyter.org)

</div>