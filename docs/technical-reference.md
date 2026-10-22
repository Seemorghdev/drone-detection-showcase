
# Small-object experiment: technical reference

[Study overview](../README.md) · [Engineering note](https://mehridian.tech/notes/small-evaluations)

This reference documents existing work. It is not an installation guide for an operational detector. No new model run or field measurement was performed for this showcase.

## What was built

The standalone Python project contains an offline inference implementation, evaluation scripts, experiment notebooks, retained result files and technical decision documents. The detector used a YOLO-based model. Image crops were evaluated in the original frame's coordinate system. The repository also contains separate geometry work; this showcase makes no position-accuracy claim and does not reproduce that functionality.

## Artifact map

| Artifact class | What it contributes | What it does not establish |
| --- | --- | --- |
| Inference source | A reviewable offline implementation | A running service or live phone application |
| Evaluation scripts and notebooks | How the author organized comparisons | A fresh execution in this review |
| Retained field summaries | Selected, manually referenced candidate observations | Blind precision/recall or general accuracy |
| Capture still | Actual appearance of an input scene | A detection, a correct selection or model quality |
| Two annotated output images | Original retained evaluation markers, including competing candidates | Autonomous identification or a new inference result |
| Recovered checkpoint | Bytes matching a retained model-reference digest | Training quality, fresh acceptance or redistribution clearance |
| Recovered training record | Stored 50-epoch history matching the notebook within rounding; historical aggregate validation metrics | Independent reproduction, drone-only accuracy or proven transfer provenance |
| Decision documents | Implementation choices and unresolved limitations | Independent validation of those choices |

## Read the result correctly

The retained report covers **eight selected field frames**. A candidate near the manual reference was reported in each. The evaluation had access to the reference marks; this is not an eight-out-of-eight autonomous identification score.

The scans also produced competing candidates. A separate operator-cued selection check succeeded in **two of four paired observations**. These are different checks with different units: do not add their counts or turn them into a single success rate.

The useful finding is that surfacing a plausible candidate and choosing the intended object are different problems. The record supports discussing that distinction, not a claim of a validated deployment.

| Retained check | Unit | Reported observation | Interpretation limit |
| --- | --- | --- | --- |
| Reference-matched candidate recovery | 8 selected frames | A candidate near the manual reference in each | Reference-assisted review; not precision, recall or autonomous identification |
| Separate operator-cued selection | 4 paired observations | 2 selections succeeded | Different task and denominator; do not combine with the frame count |
| Checkpoint identity | One recovered checkpoint | Digest matches a retained reference | Artifact identity, not training quality or fresh inference acceptance |

## Reproduction prerequisites

See the [sanitized training report](training-report.md) for the four-class validation table, separate checkpoint/notebook metric origins, dataset attribution and observed model license. The dataset's CC BY 4.0 declaration does not replace the checkpoint's AGPL-3.0 notice or certify redistribution compliance.

The original application source remains private. The recovered checkpoint and sanitized notebooks are now public through the separate Hugging Face release linked below. An archive inspection located a saved checkpoint whose SHA-256 matches a retained model-reference record. This establishes an artifact identity link, not a fresh model run. Inputs and third-party datasets have separate distribution considerations. A visitor cannot reproduce the reported result merely by copying a command from this page.

The public checkpoint and edited notebooks provide inspectable artifacts, but do not establish a complete reproducible benchmark. The environment is not locked, dataset rights and split independence require separate review, and the exploratory evaluation lacks ground-truth matching. No weights or datasets are automatically downloaded by this showcase.

## Public model and reviewed notebooks

Published 22 October 2026 on [Hugging Face](https://huggingface.co/Seemorgh/yolo11n-aod4-v6):

- [Recovered YOLO11n checkpoint and model card](https://huggingface.co/Seemorgh/yolo11n-aod4-v6); [release files](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/tree/692377dc55f682cbe5fe17fc5944514574ca9b08).
- [Sanitized training and Core ML export notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/01_train_export.ipynb): edited code with a labeled historical-results summary; original raw outputs and the credential literal are excluded.
- [Exploratory evaluation notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/02_eval_tiling_range.ipynb): an **unexecuted draft in the retained record**, with unsupported validation claims corrected.
- [Notebook review and sanitization notes](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/NOTEBOOK_REVIEW.md), including method limitations and publication edits.

The notebook links pin the reviewed release revision. Publication-file checksums identify the released bytes; they do not supply the missing original cloud-to-local transfer receipt or independently authenticate the old training run. No new training, inference, conversion or evaluation was performed for publication. Exact checkpoint-to-Core-ML equivalence and successful device inference remain unverified.

The evaluation draft implements two exploratory steps despite its original three-step title. It counts aerial predictions without matching boxes to ground truth; bird predictions are class counts, not measured false positives. Increased prediction frequency does not validate tiling, recall, a detection floor or physical range. Neither notebook establishes field reliability or on-device performance.

The model release preserves the checkpoint's AGPL-3.0 designation; dataset CC BY 4.0 attribution is separate. The links do not establish an Enterprise agreement, Apache-2.0 relicensing permission or redistribution compliance. The original application, unsanitized notebooks, raw media and operational components are not released here.

## Current access

- **Public implementation:** not released.
- **Original application implementation:** private.
- **Recovered weights and sanitized notebooks:** public on Hugging Face, as linked above; the original unsanitized notebooks remain private.
- **Hosted model endpoint:** none offered here.
- **Visuals in the overview:** screened input still and two unmodified annotated evaluation outputs, available full-size; not a fresh runtime demonstration.
- **Later monorepo:** separately inventoried, not treated as acceptance of an integrated system.

## Limits and next documentation work

No new accuracy, field reliability, live capture, autonomous selection or on-device performance result is asserted. Public redistribution of code, media and weights requires separate review. The narrow technical account can stand without exposing those materials, but it must not claim to be a self-contained demo.
