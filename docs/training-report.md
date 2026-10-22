# Airborne-object detector: recovered training results

Prepared 22 October 2026. Documentary review of retained records; no new training, inference, or evaluation was performed. This report contains no credentials, local paths, private repository links, cloud-volume identifiers, or operational integration details. It does not distribute model weights or grant a model license.

## Summary

The recovered records strongly support that the available `best.pt` checkpoint came from the retained Modal training workflow. The notebook records a completed training run, checkpoint copies, and a subsequent export. More importantly, the checkpoint's stored metric history agrees with all 50 training epochs printed in the notebook.

The recorded experiment is a four-class airborne-object detector based on Ultralytics YOLO11n, not a drone-only classifier. Its aggregate validation scores must not be described as drone-specific accuracy, independent test-set results, or field reliability.

## Checkpoint provenance

The following evidence was compared without executing notebook cells, unpickling the checkpoint, reconstructing tensors, importing model libraries, or running the model:

| Evidence | Result |
| --- | --- |
| Notebook training record | Reports completion of 50 epochs and copying the best checkpoint into retained storage |
| Notebook follow-up record | Lists best and last checkpoints, training-result files, and a subsequent model export |
| Checkpoint metadata | Identifies Ultralytics 8.4.87 and contains an AGPL-3.0 license notice |
| Recorded run identity | Checkpoint run-name text agrees with the notebook's training run |
| Epoch history | Checkpoint contains 50 epochs, numbered 1–50 |
| Metric-history comparison | All 200 values—precision, recall, mAP50, and mAP50–95 across 50 epochs—agree with notebook training rows within printed rounding precision |

The comparison used an absolute tolerance of 0.00051 for the notebook's three-decimal aggregate rows. The largest observed difference was 0.00050. This is a transcription/provenance comparison, not a performance test or statistical confidence estimate.

**Conclusion:** same-run origin is strongly supported by matching retained records. An independent, contemporaneous checksum receipt linking the original cloud artifact to the recovered local file was not located in the inspected material, so byte-for-byte transfer provenance remains unproven. Saved notebook outputs and checkpoint metadata are historical records, not independently authenticated execution receipts.

## Dataset and attribution

The notebook identifies **Airborne-Object-Detection-4-AOD4, version 6**, by **Airborne Object Detection**, hosted on Roboflow Universe. Its saved dataset configuration lists four classes: airplane, bird, drone, and helicopter.

The [public version-6 dataset page](https://universe.roboflow.com/airborne-object-detection/airborne-object-detection-4-aod4/dataset/6) agrees with the notebook's dataset identity and CC BY 4.0 notice. It lists the following split:

| Split | Published image count |
| --- | ---: |
| Training | 15,761 |
| Validation | 4,514 |
| Test | 2,241 |
| Total | 22,516 |

The notebook's validation rows report 4,514 images and 6,369 annotated instances. The image count matches the published validation split. No held-out test-set result was established during this review. Source-image provenance and cross-split duplicates were not independently audited.

Attribution for this account: Airborne Object Detection, *Airborne-Object-Detection-4-AOD4 Dataset*, version 6, Roboflow Universe; accessed 22 October 2026. Dataset images are not reproduced in this report.

## Recorded results

These are **aggregate box-detection validation metrics across four classes**. mAP50 is mean average precision at IoU 0.50; mAP50–95 averages across IoU thresholds 0.50–0.95. Neither is a simple percentage of images correctly classified.

| Metric | Checkpoint's stored training metrics | Notebook's subsequent validation output |
| --- | ---: | ---: |
| Precision | 0.94164 | 0.941, printed to three decimals |
| Recall | 0.93812 | 0.938, printed to three decimals |
| mAP50 | 0.96511 | 0.9651819355211275 |
| mAP50–95 | 0.66650 | 0.66663031065507 |

The notebook's final validation entry is separate from the training-history rows stored in the checkpoint. The small differences are retained rather than silently merged. Their cause was not established by a fresh evaluation.

The notebook also reports 50 epochs completed in 1.495 hours. This is a historical logged duration, not a fresh speed measurement or a claim about local-device performance.

Training-plot filenames appear in the saved output, but those references alone do not establish that the original plot files were recovered. No new plots have been presented as original training artifacts.

## License findings

### Dataset: CC BY 4.0 declaration verified

Both the retained dataset configuration and public dataset page declare **CC BY 4.0**. That license permits sharing and adaptation subject to its terms, including appropriate attribution, a license link, and indicating changes. It does not guarantee every underlying right or replace a source-provenance review. See the [Creative Commons license summary](https://creativecommons.org/licenses/by/4.0/).

### Model and training framework: AGPL-3.0 evidence verified

The checkpoint itself contains an **AGPL-3.0** notice. The [Ultralytics 8.4.87 source license](https://raw.githubusercontent.com/ultralytics/ultralytics/v8.4.87/LICENSE) is GNU AGPL version 3. Ultralytics' [current licensing statement](https://www.ultralytics.com/license) describes its AGPL and Enterprise licensing arrangements, including trained models.

No separate Enterprise agreement or permission to relicense these weights as Apache-2.0 was established in the inspected records. This review therefore does **not** assign an Apache-2.0 license or certify distribution compliance. Dataset licensing and model/framework licensing are separate matters; a dataset's CC BY notice does not settle the model's redistribution terms. This is a record of observed notices, not a legal opinion.

## What the results do not establish

- Drone-class precision, recall, or AP independently of the other three classes.
- General performance on unseen cameras, weather, locations, or small objects in high-resolution field footage.
- Absence of dataset leakage or scene overlap between splits.
- Real-time or mobile-device inference performance.
- Independent reproduction of the reported metrics.

The previously documented selected-frame observations and manually referenced candidate-selection checks are different tasks. Their counts must not be pooled with these validation metrics or described as an autonomous-detection success rate.

## Sanitization and availability

The source notebook contains a hard-coded credential-like value. The original notebook is excluded from this report; the separate published training notebook replaces the credential with an environment-variable reference and removes raw outputs, cloud identifiers, internal evidence links and device-specific paths. The credential was not tested; this report does not establish that it has been revoked.

This report remains a sanitized documentary account and is not redistribution clearance. The recovered checkpoint and reviewed notebook derivatives have since been published separately, as linked below. Publication does not change the historical provenance or evaluation findings.

## Public model and reviewed notebooks

Published 22 October 2026 on [Hugging Face](https://huggingface.co/Seemorgh/yolo11n-aod4-v6):

- [Recovered YOLO11n checkpoint and model card](https://huggingface.co/Seemorgh/yolo11n-aod4-v6); [release files](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/tree/692377dc55f682cbe5fe17fc5944514574ca9b08).
- [Sanitized training and Core ML export notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/01_train_export.ipynb): edited code with a labeled historical-results summary; original raw outputs and the credential literal are excluded.
- [Exploratory evaluation notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/02_eval_tiling_range.ipynb): an **unexecuted draft in the retained record**, with unsupported validation claims corrected.
- [Notebook review and sanitization notes](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/NOTEBOOK_REVIEW.md), including method limitations and publication edits.

The notebook links pin the reviewed release revision. Publication-file checksums identify the released bytes; they do not supply the missing original cloud-to-local transfer receipt or independently authenticate the old training run. No new training, inference, conversion or evaluation was performed for publication. Exact checkpoint-to-Core-ML equivalence and successful device inference remain unverified.

The evaluation draft implements two exploratory steps despite its original three-step title. It counts aerial predictions without matching boxes to ground truth; bird predictions are class counts, not measured false positives. Increased prediction frequency does not validate tiling, recall, a detection floor or physical range. Neither notebook establishes field reliability or on-device performance.

The model release preserves the checkpoint's AGPL-3.0 designation; dataset CC BY 4.0 attribution is separate. The links do not establish an Enterprise agreement, Apache-2.0 relicensing permission or redistribution compliance. The original application, unsanitized notebooks, raw media and operational components are not released here.
