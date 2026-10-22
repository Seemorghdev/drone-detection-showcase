
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
| Recovered checkpoint | Bytes matching a retained model-reference digest | Training quality, fresh acceptance or a distributable model |
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

The source repository and model weights remain private. An archive inspection located a saved checkpoint whose SHA-256 matches a retained model-reference record. This establishes an artifact identity link, not a fresh model run. Inputs and third-party datasets have separate distribution considerations. A visitor cannot reproduce the reported result merely by copying a command from this page.

A reproducible release would need a specifically reviewed source snapshot, permitted inputs, a permitted model artifact, environment information and a clear evaluation protocol. Those are missing public-release components, not something this website silently supplies. No weights or datasets are downloaded by the preview.

## Current access

- **Public implementation:** not released.
- **Implementation and model weights:** retained privately; not distributed through this website.
- **Hosted model endpoint:** none offered here.
- **Visuals in the overview:** screened input still and two unmodified annotated evaluation outputs, available full-size; not a fresh runtime demonstration.
- **Later monorepo:** separately inventoried, not treated as acceptance of an integrated system.

## Limits and next documentation work

No new accuracy, field reliability, live capture, autonomous selection or on-device performance result is asserted. Public redistribution of code, media and weights requires separate review. The narrow technical account can stand without exposing those materials, but it must not claim to be a self-contained demo.
