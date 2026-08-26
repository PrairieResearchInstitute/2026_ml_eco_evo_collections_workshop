**NOTE: Workshop Is Currently FULL**. If you want to be on the waitlist, please email [Deborah Paul](https://github.com/debpaul).
# Hands-on Workshop: Machine learning for ecology and evolution research using natural history collections

Welcome to the gitHub repository for this ML/AI event hosted by the organizing team from the INHS Species File Group at PRI. We're pleased to bring guest instructors [Bruno de Medeiros](https://orcid.org/0000-0003-1663-668X), and [Elizabeth Postema](https://orcid.org/0000-0001-5958-1071), from the Field Museum to offer this hands-on workshop. Together, we will explore machine learning tools that can be used to accelerate research using natural history collections. We will focus on two specific domains: **custom-trained image classification and detection models**, and **using language models to extract structured data from inputs like pdfs or collection labels**. We will rely on user friendly tools to show how to train and deploy image models and how to interact programmatically with large language models. We will discuss pros and cons of cloud-based tools or those that can be run locally, and options for managing costs.

- Date: August 26, 2026
- Where (in person): Forbes 1005. [Google Maps](https://maps.app.goo.gl/Rh1vDuQ6ovRS9ahi7), [Open Street Map](https://www.openstreetmap.org/way/138260147)
- Time: 900 - 500 PM
- Instructors: Bruno de Medeiros, Assistant Curator of Insects, Field Museum and Elizabeth Postema, Post Doctoral Research Scientist, Field Museum
- Helpers: [Matt Yoder](https://github.com/mjy), [Geoff Ower](https://github.com/gdower), [Deborah Paul](https://github.com/debpaul)

- Questions? Please email event organizer and member of the INHS Species File Group, Deborah Paul dlpaul@illinois.edu

## What is in this repository

**`computer_vision/`** — the images for the image-model half. There is nothing to install: we will use [Roboflow](https://roboflow.com) in your browser, and these are the pictures you will upload to it.

- **`goldenrod_visitors/upload_to_roboflow/`** — 52 photographs of insects on goldenrod. This is the training set you will annotate and train a detector on.
- **`goldenrod_visitors/new_images/`** — four more photographs, held back. Once your model is trained, run it on these to see how it does on pictures it has never seen.
- **`cicindela_trays/`** — five whole drawers of *Cicindela* tiger beetles, one species per tray. Big images with many specimens in each, for counting and for classifying at the tray scale.

There is one notebook, for after your model is trained, and a `README` of its own describing both of its parts.

| | |
| --- | --- |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/computer_vision/Coding_Demo_for_UIUC_ML_Workshop.ipynb) | **`Coding_Demo_for_UIUC_ML_Workshop.ipynb`** — deploying the model you just trained on images it has never seen, and then chaining two models together to measure every specimen in a drawer. |

You will need a Roboflow API key, but no GPU: these models run on Roboflow's servers. See [`computer_vision/README.md`](computer_vision/README.md) for the details.

**`structured_extraction/`** — the language-model half: reading PDFs and collection labels into a table. There are three Colab notebooks, and a `README` of its own with what each one does and what you need to run them.

| | |
| --- | --- |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/structured_extraction/demo.ipynb) | **`demo.ipynb`** — the whole pipeline in one call, to see where we are going. Run this first. |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/structured_extraction/workshop.ipynb) | **`workshop.ipynb`** — the session itself, building all of it from an empty cell. |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/structured_extraction/hands-on.ipynb) | **`hands-on.ipynb`** — the same pipeline on documents of your own. |

The notebooks need a Colab runtime with a GPU, and they are the reason for the Ollama install below. See [`structured_extraction/README.md`](structured_extraction/README.md) for the details.

### The data, as a download

Every notebook fetches what it needs on its own, so you do not have to do this to follow along. Download it when you want the files on your own computer — to upload the training images into Roboflow, or to keep working after the workshop. Both are in the [`v2026.08.26` release](https://github.com/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/releases/tag/v2026.08.26).

- **[computer_vision_images.zip](https://github.com/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/releases/download/v2026.08.26/computer_vision_images.zip)** (134 MB) — all 61 images, in the three folders above.
- **[example_pdfs.zip](https://github.com/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/releases/download/v2026.08.26/example_pdfs.zip)** (2 MB) — the two taxonomic papers, 2013 and 1929.

## Software
- Please sign up for a [Roboflow](https://roboflow.com/pricing) account (free level). If you need help or have questions about this, please email Elizabeth.
- From Bruno Medeiros: for his part, everything will be done with [Google Colab](https://colab.research.google.com/) notebooks and free usage, so you will only need a google drive.
- Please download and install ollama (https://ollama.com/) on your computers and create a free account there. Colab will be the workhorse but Bruno will demonstrate how we could transpose code to a local machine and for ollama cloud, so this will be helpful.

## Food
- Please bring your own lunch. We will provide snacks and drinks.
