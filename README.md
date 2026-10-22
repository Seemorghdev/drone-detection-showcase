# Small Objects in Big Frames

**Public study artifacts · historical offline observations · no runnable detector**

This repository contains the screened documentary account and original retained visual artifacts for a small-object vision experiment. It is not a release of the detector, its model weights or an operational system.

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

All 200 stored metric-history values in the recovered checkpoint agree with the notebook's 50 training epochs within printed rounding precision. This strongly supports the same-run origin, but an original byte-for-byte transfer receipt was not located. The [sanitized training report](docs/training-report.md) keeps the checkpoint's stored metrics separate from the notebook's slightly different subsequent validation scores and documents the dataset's CC BY 4.0 declaration and checkpoint's AGPL-3.0 notice. No new evaluation or model release is implied.

## Original retained output A

![Original retained output A with reference, matched-candidate and cue markers](assets/retained-output-a.png)

The marks were retained unchanged. Matching used manual references; it was not autonomous target identification. [Output B](assets/retained-output-b.png) preserves competing candidates and its original sideways orientation rather than hiding the less successful result.

## Access boundary

The implementation, weights, raw media archive, datasets, geometry and operational components remain private and are not supplied here. There is no application install command, inference endpoint, containerized detector or live camera demo. A screenshot or recorded walkthrough of these artifacts must be labeled as historical material, not a fresh run.

The owner approved these screened visuals and documentary findings for public use on 22 October 2026. Private source registers and evidence coordinates are excluded. No new open-source license for the original application or model is granted by this documentation repository.

See [SHA256SUMS.txt](SHA256SUMS.txt) for included-file integrity. Hashes establish file identity, not the truth of historical claims.
