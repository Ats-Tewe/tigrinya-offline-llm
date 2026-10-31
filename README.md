# An offline Tigrinya language model

**Status: code release in progress.**

This repository will hold the full pipeline behind an offline Tigrinya
language model: a 144.6-million-token corpus assembled from 21 native and
5 machine-translated sources, a 57,198-record Tigrinya instruction set, a
two-stage adaptation of a 7.94-billion-parameter multilingual model, and
a deployment benchmark on consumer laptops with no graphics hardware.

The code is written and the measurements are taken. What remains is the
release hygiene that has to happen before a research pipeline becomes a
public repository: removing credentials from history, pinning the
dependency set, and checking that every released data file is one the
source licence permits us to redistribute. That work is underway and the
repository will be populated when the accompanying paper is accepted.

## Already available

| | |
|---|---|
| Corpus | https://huggingface.co/datasets/Ha-Te-21/tigrinya-corpus |
| Model weights (bf16) | https://huggingface.co/Ha-Te-21/tigrinya-Gemma_4_E4B |
| Four-bit build for CPU inference | https://huggingface.co/Ha-Te-21/sft_v1_q4km |

The corpus is released per source, because the constituent sources carry
different licences and several do not permit redistribution as a single
archive.

## What will land here

- The corpus collection and cleaning pipeline: Ge'ez-script OCR repair,
  script-level language identification, near-duplicate removal, and the
  round-trip translation filter.
- The instruction-set construction scripts, including the four task types
  built deterministically from existing text.
- Both continued-pre-training stages and the supervised fine-tuning run.
- The four-arm ablation harness and both scoring harnesses, generative and
  calibrated likelihood, with each correction switchable so the documented
  failure modes can be reproduced.
- The 865-item evaluation set and its leakage audit, covering exact
  overlap, near-duplicate overlap, and the case where a passage used to
  generate an instruction item also appears in the pre-training corpus.
- The quantisation step and the deployment benchmark, with the raw result
  files from all three test machines.
- Pinned dependency versions and a reproduction guide.

## Licence

Code will be released under the MIT licence. The adapted model is a
derivative of Gemma and its redistribution is governed by the Gemma Terms
of Use. Corpus sources retain their own licences, recorded per source.

## A condition on use

This model should not be presented as a source of factual information
about the world. Its hallucination rate has not been measured. It is a
Tigrinya language model that follows instructions and formats output
reliably, and it is at its best when the answer is in the text supplied to
it rather than in its weights.

## Contact

Atsbaha Teweldemedhn Hagos — atsbaha.teweldemedhn@mu.edu.et
Software Engineering, Mekelle University, Mekelle, Ethiopia

Watch this repository to be notified when the code lands.
