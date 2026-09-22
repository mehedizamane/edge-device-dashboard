# Edge Models

[![Live dashboard](https://img.shields.io/badge/Live_dashboard-GitHub_Pages-1f6feb?logo=github)](https://mehedizamane.github.io/edge-device-dashboard/) [![Catalog](https://img.shields.io/badge/Catalog-15_models-202124)](https://mehedizamane.github.io/edge-device-dashboard/#catalog)

**Edge Models** is a research-oriented field guide to small and mobile-ready AI models. It brings together model access, mobile memory estimates, practical phone floors, use cases, primary documentation, and a deliberately cautious benchmark atlas for people evaluating on-device AI.

**Dashboard:** https://mehedizamane.github.io/edge-device-dashboard/

> This is a comparative reference, not a benchmark suite or a hardware compatibility guarantee. Scores and resource estimates are reported from the cited primary material and should be validated on the exact runtime, model variant, and device being deployed.

## What is in the dashboard?

The catalog covers 15 models and SDKs spanning local language models, multilingual translation, speech recognition, wake-word detection, and OS-integrated models. It includes:

- **Catalog:** access model, mobile profile, reported memory range, minimum-spec phone examples, and primary use cases.
- **Quick picks:** task-oriented paths for small-footprint utility, multilingual work, private audio, and heavier reasoning.
- **Hardware guide:** a RAM-first way to narrow options before comparing model capability.
- **Benchmark snapshot:** a like-for-like MMLU 5-shot chart plus an atlas that keeps other results inside their relevant capability families.
- **Technical sources:** a source registry linking each catalog item to an official model card, paper, SDK document, or product page.

## Using the dashboard

1. Open the [live site](https://mehedizamane.github.io/edge-device-dashboard/).
2. Start at **Quick picks** if you have a task in mind, or use the catalog’s **access** and **phone RAM** filters to narrow the list.
3. Treat **Minimum spec phones** as practical starting points—not certified compatibility claims. Device memory available to an app depends on the OS, background applications, context length, and inference runtime.
4. Select a model name in the catalog to open its source and notes.
5. Use **Benchmark snapshot** only for comparisons that share the same benchmark and protocol. The MMLU chart is ordered descending because higher accuracy is better; speech WER is separately labeled lower-is-better.
6. Follow the **Technical sources** links before making a deployment decision, especially for licensing, supported languages, quantization, and runtime restrictions.

## Reading the data responsibly

### Resource estimates

The `Memory` column is a reported working-memory range, not a universal RAM requirement. In practice, it changes with precision (for example, FP16 versus INT4), runtime, KV cache/context window, batch size, available accelerator memory, and other apps. Phone examples communicate a pragmatic floor from the review; they are not vendor endorsements.

### Access labels

| Label | Meaning in this catalog |
| --- | --- |
| Open Weight | Weights are available under a model-specific license. Availability does not imply unrestricted commercial use. |
| Closed (OS) | Model capability is delivered through a device operating system and is subject to hardware and software eligibility. |
| Commercial SDK | A vendor SDK or packaged model artifact is available; terms and deployment support are vendor-defined. |

### Benchmark policy

Model scores are not interchangeable just because they are percentages. Each result retains its original task, model variant, prompt format, precision, split, and metric where reported. The dashboard therefore:

- charts only the three published **MMLU 5-shot** instruction-model results together;
- groups non-comparable scores by capability family rather than assigning a synthetic overall ranking;
- keeps **WER** in a lower-is-better speech group;
- records wake-word detection by its fixed false-alarm operating point rather than inventing one universal score; and
- does not assign comparable scores to Apple Intelligence or Gemini Nano where a reproducible public standard-score table was not found.

Reported benchmarks are model-card or paper results, not measurements made by this project. They should not be read as latency, battery, privacy, safety, or end-to-end application quality results.

## Catalog scope

| Area | Catalog entries |
| --- | --- |
| General LLMs | SmolLM2, Llama 3.2, Qwen 2.5 / Qwen 3, Gemma 2 / Gemma 3n, Phi-3.5 / Phi-4 Mini, MobileLLM, Liquid LFM2 / LFM2.5, Mistral NeMo 8B |
| Multilingual | Tiny Aya, Qwen, Llama 3.2 |
| Speech and voice | Cohere Transcribe, Whisper Tiny / Base, Picovoice Porcupine |
| Specialized mobile SDKs | Desert Ant Micro-SDKs |
| OS-integrated models | Apple Intelligence Model, Gemini Nano |

The project is intentionally selective rather than exhaustive. Inclusion indicates that an entry is relevant to on-device or mobile evaluation; it is not a recommendation or a claim of equal maturity across categories.

## Source index

The dashboard links each entry directly. The same primary sources are collected here for repository readers.

| Model / system | Primary documentation |
| --- | --- |
| Cohere Transcribe | [Cohere product page](https://cohere.com/transcribe) · [benchmark announcement](https://cohere.com/blog/transcribe) |
| Tiny Aya | [Cohere documentation](https://docs.cohere.com/docs/tiny-aya) · [technical report](https://arxiv.org/abs/2603.11510) |
| Apple Intelligence | [Apple developer documentation](https://developer.apple.com/apple-intelligence/) |
| Gemini Nano | [Google product documentation](https://store.google.com/us/magazine/gemini-nano-offline?hl=en-US) |
| SmolLM2 | [Hugging Face model card](https://huggingface.co/HuggingFaceTB/SmolLM2-1.7B-Instruct) |
| Llama 3.2 | [Meta / Hugging Face model card](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct) |
| Qwen 2.5 / Qwen 3 | [Qwen 2.5 model card](https://huggingface.co/Qwen/Qwen2.5-3B-Instruct-GGUF) · [evaluation table used for MMLU-redux](https://huggingface.co/Qwen/Qwen2.5-Omni-3B) |
| Gemma 2 / Gemma 3n | [Google Gemma documentation](https://ai.google.dev/gemma) · [Gemma 3n model card](https://ai.google.dev/gemma/docs/gemma-3n/model_card) |
| Phi-3.5 / Phi-4 Mini | [Microsoft Phi-3.5 model card](https://huggingface.co/microsoft/Phi-3.5-mini-instruct) |
| MobileLLM | [Meta Research repository](https://github.com/facebookresearch/MobileLLM) |
| Desert Ant Micro-SDKs | [Desert Ant documentation](https://desertant.com/) · [Tongue benchmark documentation](https://desertant.com/docs/tongue/) |
| Whisper Tiny / Base | [Whisper paper](https://cdn.openai.com/papers/whisper.pdf) · [Qualcomm AI Hub model documentation](https://aihub.qualcomm.com/models/whisper_tiny) |
| Picovoice Porcupine | [Picovoice documentation](https://picovoice.ai/) · [wake-word benchmark harness](https://github.com/Picovoice/wake-word-benchmark) |
| Liquid LFM2 / LFM2.5 | [Liquid AI demos and documentation](https://demos.liquid.ai/) · [LFM2 technical report](https://arxiv.org/abs/2511.23404) |
| Mistral NeMo 8B | [NVIDIA Mistral-NeMo Minitron model card](https://huggingface.co/nvidia/Mistral-Nemo-Minitron-8B-Instruct) |

## Reproducing the website

This repository is a dependency-free static website. No model weights, user data, telemetry, or server-side code are included.

```powershell
git clone https://github.com/mehedizamane/edge-device-dashboard.git
cd edge-device-dashboard
python -m http.server 8000
```

Then open `http://127.0.0.1:8000/`. Editing `index.html`, `styles.css`, or `app.js` is enough to update the site.

## Acknowledgment

The dashboard format draws inspiration from research-facing benchmark and model repositories that pair a concise project overview with explicit evaluation context, reproducibility guidance, and source-linked artifacts, including [SciConBench](https://sciconbench.cs.princeton.edu/) and [OLMo](https://github.com/allenai/OLMo).
