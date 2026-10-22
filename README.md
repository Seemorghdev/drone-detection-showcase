# Small Objects in Big Frames

**Public study artifacts · historical offline observations · no runnable detector**

This repository contains the screened documentary account and original retained visual artifacts for a small-object vision experiment. The showcase itself remains documentary; a separate Hugging Face release now provides the recovered checkpoint and sanitized notebooks. The original detector application and operational system are not released here.

## Inspect the work

- [Technical reference](docs/technical-reference.md)
- [Recovered training report and recorded validation results](docs/training-report.md)
- [Retained observations and limits](docs/observations.md)
- [Visual provenance](docs/visuals.md)
- [Portfolio account](https://mehridian.tech/projects/small-object-detection)

| Retained check | Unit | Reported observation | Limit |
| --- | --- | --- | --- |
| Manually reference-matched candidate recovery | 8 selected frames | A candidate near the reference in each | Not autonomous identification or general accuracy |
| Separate operator-cued selection | 4 paired observations | 2 selections succeeded | Different task and denominator; not added to the frame count |
| Checkpoint identity | One recovered file | Digest matches a retained reference | Artifact identity, not training quality or fresh inference |

No new experiment was run to create this repository. These are retained observations, not a newly reproduced benchmark.

## Recovered training record

The retained Modal notebook reports **mAP50 0.96518** and **mAP50–95 0.66663** on **4,514 validation images**, aggregated across airplane, bird, drone and helicopter classes. These are recorded validation metrics, not drone-only accuracy or field reliability.

All 200 stored metric-history values in the recovered checkpoint agree with the notebook's 50 training epochs within printed rounding precision. This strongly supports the same-run origin, but an original byte-for-byte transfer receipt was not located. The [sanitized training report](docs/training-report.md) keeps the checkpoint's stored metrics separate from the notebook's slightly different subsequent validation scores and documents the dataset's CC BY 4.0 declaration and checkpoint's AGPL-3.0 notice. No new evaluation is implied; the separate artifact release is linked below.

## Public model and reviewed notebooks

Published 22 October 2026 on [Hugging Face](https://huggingface.co/Seemorgh/yolo11n-aod4-v6):

- [Recovered YOLO11n checkpoint and model card](https://huggingface.co/Seemorgh/yolo11n-aod4-v6); [release files](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/tree/692377dc55f682cbe5fe17fc5944514574ca9b08).
- [Sanitized training and Core ML export notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/01_train_export.ipynb): edited code with a labeled historical-results summary; original raw outputs and the credential literal are excluded.
- [Exploratory evaluation notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/02_eval_tiling_range.ipynb): an **unexecuted draft in the retained record**, with unsupported validation claims corrected.
- [Notebook review and sanitization notes](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/NOTEBOOK_REVIEW.md), including method limitations and publication edits.

The notebook links pin the reviewed release revision. Publication-file checksums identify the released bytes; they do not supply the missing original cloud-to-local transfer receipt or independently authenticate the old training run. No new training, inference, conversion or evaluation was performed for publication. Exact checkpoint-to-Core-ML equivalence and successful device inference remain unverified.

The evaluation draft implements two exploratory steps despite its original three-step title. It counts aerial predictions without matching boxes to ground truth; bird predictions are class counts, not measured false positives. Increased prediction frequency does not validate tiling, recall, a detection floor or physical range. Neither notebook establishes field reliability or on-device performance.

The model release preserves the checkpoint's AGPL-3.0 designation; dataset CC BY 4.0 attribution is separate. The links do not establish an Enterprise agreement, Apache-2.0 relicensing permission or redistribution compliance. The original application, unsanitized notebooks, raw media and operational components are not released here.

## Original retained output A

![Original retained output A with reference, matched-candidate and cue markers](assets/retained-output-a.png)

The marks were retained unchanged. Matching used manual references; it was not autonomous target identification. [Output B](assets/retained-output-b.png) preserves competing candidates and its original sideways orientation rather than hiding the less successful result.

## Access boundary

The original application implementation, raw media archive, datasets, geometry and operational components remain private. The recovered weights and edited notebooks are available through the separate Hugging Face release above; they are not bundled in this repository. There is no application install command, inference endpoint, containerized detector or live camera demo. A screenshot or recorded walkthrough of these artifacts must be labeled as historical material, not a fresh run.

The owner approved these screened visuals and documentary findings for public use on 22 October 2026. Private source registers and evidence coordinates are excluded. No new open-source license for the original application or model is granted by this documentation repository.

See [SHA256SUMS.txt](SHA256SUMS.txt) for included-file integrity. Hashes establish file identity, not the truth of historical claims.
