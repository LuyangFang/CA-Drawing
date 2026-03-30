
## Zero-Shot VLM Pilot Result for Item 1

To provide comparison with a modern open-source vision–language model (VLM), we conducted a pilot zero-shot evaluation on Item 1 (`task42`; red dye diffusion) using **Qwen3-VL-8B-Instruct**. The model was evaluated on the same task-specific test split used by the ViT experiments, following the same stratified 80/10/10 partition with seed 42. No task-specific fine-tuning was applied. The prompt included the item-specific rubric, reference graphs, and student drawing, and the model was required to return a rubric label in a parseable boxed format. All 48 test responses were successfully parsed.

### Results

| Method | Acc. | Kappa | Prec. | Rec. | F1 | Latency (ms) |
|--------|------|-------|-------|------|----|--------------|
| Zero-shot Qwen3-VL-8B-Instruct | 0.479 | 0.417 | 0.310 | 0.508 | 0.385 | 9733.87 |

**Table:** Zero-shot VLM pilot result on Item 1 (`task42`) using the same test split as the ViT experiments. Latency is reported as the average per-sample inference time on a single NVIDIA A100 GPU.

This pilot result provides a preliminary multimodal reference point for Item 1. Compared with the frozen ViT baseline reported in the main paper, the zero-shot VLM achieves substantially stronger agreement with human scoring, but it remains below the fine-tuned and confidence-aware ViT variants while incurring much higher inference latency.
