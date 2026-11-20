# <HFpEF ECG model>

> Created from the CVDLINK **model-template**. Fill in the placeholders below, then work
> through [PUBLISHING.md](PUBLISHING.md) to release this model to Zenodo → OpenAIRE → EOSC.
> Delete this note once everything is published (PUBLISHING.md stage 8).

## What it is

A VCG-based machine learning model for Heart Failure classification in subjects with Sinus rhythm.

This model performs multitask classification of normals vs HF subjects &ndash; HFpEF (EF ≥ 50%) and HFrEF (EF < 50%).

To develop this model, open access data were retrieved from Physionet: PTB Diagnostic ECG Database, MUSIC (Sudden Cardiac Death in Chronic Heart Failure)

## Status

`experimental`  <!-- one of: experimental | prototype | stable | archived -->

## Inputs / outputs

- **Input:** VCG signals in WFDB format (.dat/.hea) with sampling frequency of 500Hz or above (model was trained on 1000Hz recordings)
- **Output:** JSON object describing the probability of the patient belonging to each class

## Install / run
### 1. Load the Docker image
```bash
docker load -i hfpef-preprocessing-inference.tar
```

### 2. Run the pipeline
```bash
docker run hfpef-preprocessing-inference
```

### 3. View results

Results will be saved inside the container at `/03_output/`

To save results to your computer:
```bash
docker run -v %cd%/python:/02_code/python -v %cd%/output:/03_output hfpef-preprocessing-inference
```

Results will appear in the `output/` folder (.json file).

## Model documentation

The model is described by an **AI Card**: what it does, the data and cohort it was built on, how
it was evaluated, its limitations, and — for a system used on people — its risk profile. The card
is generated from the model description file and lives in this repo, so it is versioned with the
model and archived with each release.

- **AI Card:** [`ai-model/model-description.html`](ai-model/model-description.html)
- **AIMe registry:** <add the registry link once the record is submitted.>

## Maintainer

Ioannis Marios Karagiannis, ikaragij@auth.gr
Ioanna Chouvarda, ioannach@auth.gr

## How to cite

Once this repo is archived to Zenodo, add the DOI here (citation metadata lives in `.zenodo.json`).

<!-- Optional: if the model is also listed on the AI4EOSC Marketplace
     (see ai-model/AI4EOSC.md), add that link here too. -->
- **Run it:** <AI4EOSC Marketplace link — delete this line if not listed>
