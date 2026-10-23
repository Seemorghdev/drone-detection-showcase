# What the saved evaluation counted—and what it did not

An edited historical-results summary, prepared 23 October 2026. No new experiment,
model inference, training or dataset download was performed for this account.

A retained evaluation notebook contains saved outputs from a past run. Those outputs
add execution history to the study, but they are not an independently reproduced
benchmark. The original notebook and its raw logs remain private. The separate
[public exploratory notebook](https://huggingface.co/Seemorgh/yolo11n-aod4-v6/blob/692377dc55f682cbe5fe17fc5944514574ca9b08/notebooks/02_eval_tiling_range.ipynb)
is an edited draft derivative, not a byte-identical copy of this executed companion.

## Image-level counts, grouped by annotation size

The saved output reports a test split of 2,625 images and evaluates its first 500
entries—not a documented random sample. Images are grouped by the longest side of
their largest annotated box. The numerator counts images containing any prediction
in the script's aerial-object grouping; it does not require the prediction to match
that annotated box.

| Largest annotated-box side | Images with an aerial prediction | Images in bucket |
| --- | ---: | ---: |
| 0–10 px | 1 | 6 |
| 10–20 px | 37 | 67 |
| 20–40 px | 88 | 120 |
| 40–80 px | 76 | 98 |
| 80–160 px | 44 | 68 |
| 160+ px | 86 | 141 |

These are the original bucket labels. Their image counts sum to 500. They are
prediction-presence counts, not measured recall, accuracy or a detection floor.
The method does not perform box matching or ground-truth class filtering for this
count. A prediction elsewhere in an image can therefore contribute to its numerator.

The output also records **18 bird-class detections across the 500 sampled images**.
That counts predicted boxes, not images with birds. It is neither a false-positive
count established against ground truth nor a 3.6% image-level false-positive rate.

## One saved video comparison

The companion also prints one video result for 200 sampled frames under each listed
configuration. The source selects the first located video, while the printed basename
does not uniquely identify its dataset sequence. A stable input-video hash and
execution-time checkpoint digest are not recorded in that result.

| Configuration label in the retained output | Frames with an aerial prediction | Sampled frames | Bird-class detections |
| --- | ---: | ---: | ---: |
| Whole frame (1×1) | 109 | 200 | 0 |
| Grid variant (3×3) | 55 | 200 | 0 |
| Grid variant (6×6) | 0 | 200 | 6 |

The saved run shows fewer frames with aerial predictions for the grid variants. It
does **not** measure whether any of those predictions were correct: no frame-level
ground-truth matching is performed. Higher or lower prediction frequency cannot, by
itself, establish better or worse detection quality. These rows are not a configuration
recommendation or a validated false-positive comparison.

This output does **not** reproduce the separate historical “7% → 22%” table. The
records must remain distinct; their input identities and methods have not been
reconciled into one reproducible benchmark.

## What this adds to the project

The executed companion shows that saved run outputs exist, rather than only a blank
evaluation draft. It does not turn exploratory counters into performance metrics.
The draft and companion differ in two of six code cells, and saved execution counts
are not proof of a clean, independently authenticated run.

Keep these observations separate from the selected, manually referenced field images
and from the model's aggregate training-validation scores. This summary makes no
claim about field reliability, autonomous identification, physical range, comparative
model superiority or successful on-device inference.

The transcribed counts are available in [structured form](recorded-evaluation-counts.json).
They make this edited summary inspectable; they do not replace the private originals
or independently authenticate their historical results. See the
[training report](training-report.md) and [technical reference](technical-reference.md)
for the separate model, provenance and licensing boundaries.
