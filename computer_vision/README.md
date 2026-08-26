# Training and deploying image models

The image half of the workshop. The training itself happens in
[Roboflow](https://roboflow.com), in your browser — there is nothing to install.
The notebook comes after: it takes the model you just trained and runs it on
images it has never seen, from Python.

## The notebook

| | |
| --- | --- |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/blob/main/computer_vision/Coding_Demo_for_UIUC_ML_Workshop.ipynb) | **`Coding_Demo_for_UIUC_ML_Workshop.ipynb`** — deploying a trained model on new data. **Part A** runs your own flower-visitor detector over the held-back images, draws the boxes, crops out each detection, and writes the counts to a CSV. **Part B** chains two models from [DrawerDissect](https://github.com/EGPostema/DrawerDissect) — detect, then segment — to measure every specimen in a drawer and compare body size across species. |

## The images

All of them, as one zip:
**[computer_vision_images.zip](https://github.com/PrairieResearchInstitute/2026_ml_eco_evo_collections_workshop/releases/download/v2026.08.26/computer_vision_images.zip)** (134 MB, 61 images, folders kept as below).

- **`goldenrod_visitors/upload_to_roboflow/`** — 52 photographs of insects on
  goldenrod. The training set: these are the ones you annotate in Roboflow and
  train the detector on, so you will want them on your own computer.
- **`goldenrod_visitors/new_images/`** — four more photographs, held back from
  training. Part A runs your finished model on these.
- **`cicindela_trays/`** — five whole drawers of *Cicindela* tiger beetles, one
  species per tray. Large images with many specimens in each; Part B measures
  every specimen in all five.

The notebook fetches these itself when you run it, so the download is for
Roboflow — and for having the pictures to hand afterwards.

## What you need

A free [Roboflow](https://roboflow.com/pricing) account and its API key
(Settings → API Keys), which the notebook reads from Colab's secrets manager
under the name `ROBOFLOW_API_KEY` — never pasted into a cell. No GPU: the models
run on Roboflow's servers, and the notebook only sends images and draws what
comes back.

## Citation

> Postema, E.G., Briscoe, L., Harder, C., Hancock, G.R.A., Guarnieri, L.D,
> Eisel, T., Welch, K., Fisher, N., Johnson, C., Souza, D., Sepulveda, T.,
> Phillip, D., Baquiran, R., de Medeiros, B.A.S. 2025. DrawerDissect:
> Whole-drawer insect imaging, segmentation, and trait extraction using AI.
> EcoEvoRxiv (pre-print). https://doi.org/10.32942/X2QW84
