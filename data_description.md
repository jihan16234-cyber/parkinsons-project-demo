# Dataset Description (Update 1)

**Added by:** Afid Mostakim Ony

> **Status:** The dataset is not yet in the repository. This file describes the data the project **plans** to use. The images, the exact source and the final counts will be added with the training step in Update 2.

## What the data is
Hand-drawn images of two drawing types, used to tell people with Parkinson's disease apart from healthy people (tremor and shaky strokes show up in the drawing):

| Type | Task | Image size used in the project |
|------|------|--------------------------------|
| Spiral | Draw a spiral | 128 x 128 pixels |
| Wave | Draw a wave | 256 x 128 pixels |

Each image belongs to one of two classes:
- `healthy`
- `parkinson`

## Folder layout
```
data/
  spiral/
    training/
      healthy/*.png
      parkinson/*.png
    testing/
      healthy/*.png
      parkinson/*.png
  wave/
    training/ ...
    testing/ ...
```

The first 3 characters of each file name are the subject (person) ID, for example `V01`. This is used later so that drawings from the same person never appear in both training and testing.

## Planned dataset size
| Type | Split | Healthy images | Parkinson images |
|------|-------|----------------|------------------|
| Spiral | training | 36 | 36 |
| Spiral | testing | 15 | 15 |
| Wave | training | 36 | 36 |
| Wave | testing | 15 | 15 |

**Total:** 204 images (102 spiral + 102 wave), balanced between `healthy` and `parkinson` in every split. These are the planned counts from the project plan and will be re-checked against the real files in Update 2.

**Source of the dataset:** To be confirmed and added in Update 2 (dataset name and link).

## Notes
- The dataset is small (204 images), so results will also be checked on people the model has never seen.
- The images are not stored in this Update 1 repository. They will be added as `data.zip` with the training step (Update 2); `.gitignore` excludes the extracted `data/` folder because the code rebuilds it from the zip (`ensure_data` in `common.py`).
- This is an educational demo, not a medical diagnosis tool.
