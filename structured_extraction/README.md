# Extracting structured data from PDFs with open models

The language-model half of the workshop. We will use a free Google Colab session to run everything. 

## The notebooks

We will start with the demo to demonstrate capabilities, and then break it down in steps in the workshop. Finally, hands-on will allow students to try out on their own data.

| | |
| --- | --- |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/structured_extraction/demo.ipynb) | **`demo.ipynb`** — one function, three arguments, a table out. Ten minutes, mostly model download. Run this first. |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/structured_extraction/workshop.ipynb) | **`workshop.ipynb`** — the session itself. Four sessions building all of it from an empty cell, ending with an agent that decides how to read a page. |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/structured_extraction/hands-on.ipynb) | **`hands-on.ipynb`** — the same pipeline on documents of your own, whether PDFs or photos of labels and notes. Every function from the workshop in one block, then your folder, your prompts, your schema, and the JSON and the table it gives back. |

## The other files

- **`pdf_extraction.py`** — the finished pipeline, and the only thing `demo.ipynb`
  imports. `extract_folder(folder, prompt, schema)` asks a reasoning model, for
  each PDF, whether that document's own text can be trusted or whether the pages
  have to be re-read from their images, says what it decided and why, and gives
  you back one table. You can use it on your own folders after the workshop!
- **`example_pdfs/`** — the two papers we will work on, both taxonomic: a 2013 one
  born digital, and a 1929 one scanned from paper.
- **`.gitignore`** — keeps your own documents and everything the notebooks write
  (`processed/`, `my_results.json`, `my_results.csv`) out of the git repository.

## Models

We will use two LLMs during the workshop.

| model | role | size |
| --- | --- | --- |
| `qwen3.5:4b` | reasoning, extraction, tool use | 3.4 GB |
| `deepseek-ocr` | page transcription | 6.7 GB |

`demo.ipynb` uses the bigger `qwen3.5:9b` (6.6 GB) instead, so pull that one too
if you want to run the demo locally. The 9B and
[`gemma3:12b`](https://ollama.com/library/gemma3) (8.1 GB) are both more accurate
than the 4B, and `hands-on.ipynb` lets you switch to either if you have the
memory.

## What you need

A Google account, and a Colab runtime **with a GPU**
(Runtime → Change runtime type → T4). Colab sometimes refuses free GPUs at busy
times; if that happens, pair up with a neighbour.

To run locally instead you need [Ollama](https://ollama.ai) ≥0.32 — earlier
versions cannot load these models — then `ollama pull` both models above,
`ollama serve`, and `pip install ollama pymupdf pandas pillow`.

You will need at least 8 GB of local GPU memory for the two models above, and about 16 GB for the 9B the demo uses. If you have more, you will be able to use more powerful models.
