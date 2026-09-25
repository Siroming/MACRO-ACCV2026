# MACRO: Occlusion-Robust Single-Shot Whole-Body Mesh Recovery via Multi-Anchor Context Refinement

**ACCV 2026**

Recovering multiple people's whole-body meshes from a single image is difficult when people overlap, body parts are truncated, or hands are small. A head-only person entry can miss someone whose head is hidden, while global context and local hand evidence can become unreliable under occlusion. MACRO addresses these challenges in a single-shot SMPL-X framework without separate person or hand crop pipelines.

## Method

MACRO combines three complementary components:

- **Multi-Entry person querying** uses head and pelvis anchors as alternative entries into the decoder, followed by cross-entry deduplication.
- **Entry-Aware Context Mamba** propagates information across spatially separated visible regions through a gated, bidirectional state-space adapter.
- **Wrist-centered HandAttn** retrieves local evidence around predicted wrists and applies gated residual hand-pose refinements.

## Highlights

Under the paper's unified evaluation on 3DPW, EHF, BEDLAM, and AGORA, MACRO ranks among the top three on 15 of 16 reported metrics. Compared with the released Multi-HMR-896 checkpoint, it reduces AGORA NMVE from 79.4 to 71.7, raises F1 from 89.2% to 92.6%, and raises recall from 81.6% to 88.9%. This comparison uses different training data and is not a controlled ablation.

On AGORA, recall gains over the baseline reach 8.04 and 9.91 percentage points in the 50-70% and 70-90% occlusion groups, respectively. These results illustrate the benefit of complementary person entries in crowded scenes.

Code and pretrained weights are being prepared for release.
