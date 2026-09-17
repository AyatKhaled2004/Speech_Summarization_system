# AI Text Summarization System

An AI-based text summarization system built with **Python, PyTorch, Hugging Face Transformers, and Gradio**.

The project uses a **T5-based sequence-to-sequence model** to generate concise summaries from input text and provides an interactive interface through Gradio.

## Project Overview

The system takes user-provided text, applies basic text cleaning, processes it with a trained T5 tokenizer and summarization model, and generates a summarized response.

The application also provides a simple conversational-style interface through Gradio.

## Features

* Text preprocessing and cleaning
* T5-based text summarization
* Automatic selection of CPU or CUDA device
* Configurable text generation settings
* Streaming-style output in the Gradio interface
* Interactive web-based UI using Gradio

## How It Works

The current application follows this pipeline:

```text
User Input
    ↓
Text Cleaning
    ↓
T5 Tokenization
    ↓
Trained T5 Summarization Model
    ↓
Text Generation
    ↓
Decoded Summary
    ↓
Gradio Interface
```

## Text Preprocessing

Before being sent to the model, the input text is cleaned by:

* Replacing line breaks with spaces
* Removing repeated whitespace
* Removing HTML-like tags
* Converting text to lowercase
* Removing leading and trailing spaces

## Model

The application uses:

* `T5Tokenizer`
* `T5ForConditionalGeneration`

The tokenizer and trained summarization model are loaded from local files.

The model is moved automatically to:

```text
CUDA
```

when a compatible GPU is available; otherwise, it runs on:

```text
CPU
```

## Text Generation

The current application uses the following generation settings:

```python
max_length=175
num_beams=4
do_sample=True
temperature=0.7
```

Input text is tokenized with a maximum input length of:

```python
max_length=512
```

## User Interface

The application uses **Gradio** to provide an interactive interface titled:

```text
🧠 AI Text Summarizer
```

The interface is implemented using `gr.ChatInterface` and includes custom styling for the application container.

## Technologies Used

| Technology                | Purpose                              |
| ------------------------- | ------------------------------------ |
| Python                    | Programming language                 |
| PyTorch                   | Model loading and inference          |
| Hugging Face Transformers | T5 tokenizer and summarization model |
| Gradio                    | Interactive user interface           |
| SentencePiece             | Tokenization dependency              |

## Project Structure

```text
Speech_Summarization_system/
│
├── APP/
│   └── app.py
│
├── Notabook/
│   └── Project notebooks
│
├── Saved_model/
│   └── summarization_model/
│
├── requirements.txt
└── .gitignore
```

## Installation

Clone the repository:

```bash
git clone https://github.com/AyatKhaled2004/Speech_Summarization_system.git
cd Speech_Summarization_system
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

The required packages are:

```text
gradio
transformers
torch
sentencepiece
```

## Running the Application

The main application is located at:

```text
APP/app.py
```

Run it with:

```bash
python APP/app.py
```

### Important Note

The current `APP/app.py` loads the tokenizer and summarization model from paths under:

```text
saved_files/
```

Make sure the local model and tokenizer paths match the paths defined in the application before running it.

## Repository Contents

### `APP/`

Contains the application code and Gradio interface.

### `Notabook/`

Contains the project notebook(s).

### `Saved_model/`

Contains the saved summarization model files available in the repository.

## Current Status

The repository currently contains:

* The application interface
* The summarization inference code
* Project notebook(s)
* Saved summarization model files
* Required Python dependencies

## Author

**Ayat Khaled**

GitHub:
https://github.com/AyatKhaled2004
