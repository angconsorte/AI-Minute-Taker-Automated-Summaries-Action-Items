# AI-Minute-Taker-Automated-Summaries-Action-Items
An automated, zero-cost pipeline that transforms meeting audio into structured executive summaries. Engineered on Google Colab using Python, Faster-Whisper, and a 4-bit quantized Mistral 7B LLM.

## Situation (The Challenge)
As a CTO in the **AU Investment Club**, I noticed a critical operational gap: valuable financial analysis and strategy discussions were often lost the moment our meetings ended. We had hours of knowledge and ideas that were not taken advantage of, also making it impossible for absent members to catch up and difficult for our marketing team to create social media content or documentation.

## Task (The Objective)
My goal was to engineer an **automated pipeline** that could ingest these raw audio/video files and output accurate, structured executive summaries.

**The Constraints:**
* **Zero-Cost:** It had to avoid paid APIs and software (like Otter.ai).
* **Accessibility:** It had to run entirely on cloud infrastructure to not depend on hardware (Google Colab).

## Action (The Solution)
I built a custom Python pipeline in **Google Colab** that utilizes state-of-the-art open-source AI:

* **Optimized Transcription:** I implemented `faster-whisper` instead of the standard OpenAI library. This decision increased transcription speed by **4x**, allowing 1-hour meetings to be processed within the free Colab runtime limits.
* **Resource-Constrained LLM:** I integrated **Mistral 7B** for summarization. To fit this massive model into the 16GB VRAM limit of a free T4 GPU, I utilized **4-bit quantization** (`bitsandbytes`), compressing the model without sacrificing reasoning capabilities.
* **Prompt Engineering:** Designed a custom system prompt to extract key decisions and action items specifically for financial contexts.

## Result (The Impact)
The tool transformed our knowledge that would be wasted into a versatile content engine:
* **Increased Engagement:** Automated "Executive Summaries" allowed absent members to stay aligned on portfolio decisions instantly.
* **Content Generation:** Transcripts provided raw text for our marketing team, streamlining the creation of social media posts.
* **Automated Documentation:** We established a searchable text archive of all club decisions, eliminating the need for a manual note-taker.

---

## Tech Stack
* **Language:** Python
* **AI Models:** Faster-Whisper (ASR), Mistral-7B-Instruct (LLM)
* **Libraries:** `transformers`, `accelerate`, `bitsandbytes`, `ffmpeg`
* **Infrastructure:** Google Colab (Free Tier NVIDIA T4)

---
*This project was developed using an AI-assisted workflow to optimize library dependencies and prompt engineering.*
