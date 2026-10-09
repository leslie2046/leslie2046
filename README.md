# Hi, I'm Leslie 👋

I build Dify plugins, RAG integrations, and model-serving infrastructure, with upstream contributions to Dify, Xinference, and RAGFlow.

## Dify Plugin Collection

* **[RAGFlow](https://github.com/leslie2046/dify-ragflow-plugin)**: Connect Dify to RAGFlow for datasets, documents, chunks, retrieval, and memory workflows.
* **[Lingua](https://github.com/leslie2046/dify-plugin-lingua)**: Detect languages with ISO language-code output and optional language scoping. [Dify Marketplace](https://marketplace.dify.ai/plugins/leslie2046/lingua)
* **[MinIO](https://github.com/leslie2046/dify-plugin-minio)**: Read, upload, list, and inspect objects in MinIO-backed AI workflows.
* **[Knowledge](https://github.com/leslie2046/dify-knowledge-plugin)**: Use existing Dify knowledge-base operations inside plugin workflows.
* **[Moderation](https://github.com/leslie2046/moderation_plugin)**: Moderate Dify app input and output with configurable keywords, preset responses, and keyword masking.
* **[Juhe](https://github.com/leslie2046/dify-plugin-juhe)**: Access weather, exchange rates, oil and gold prices, and stock-market data through Juhe APIs.

## Agent Skills

* **[skills](https://github.com/leslie2046/skills)**: Reusable agent skills for the workflows I use and maintain.

## Selected Open Source Contributions

Representative merged PRs, from retrieval performance to distributed model serving.

### [Dify](https://github.com/langgenius/dify)

* **[Knowledge retrieval performance #42673](https://github.com/langgenius/dify/pull/42673)**: Cache parsed provider declarations, check query embedding caches before constructing models, and reuse rerank model metadata; the PR's 100-request benchmark reported **42.2% lower mean latency** and **73.7% lower P95 latency**.
* **[Chatflow startup performance #36773](https://github.com/langgenius/dify/pull/36773)**: Reuse request-scoped provider metadata and runtime objects to reduce repeated model resolution; the PR's local benchmark reported **41.3% lower mean workflow startup latency**.
* **[Excel image ingestion #37104](https://github.com/langgenius/dify/pull/37104)**: Extract embedded images from `.xlsx` knowledge imports, store them as uploaded files, and preserve image-only rows for downstream indexing.

[All merged Dify PRs](https://github.com/langgenius/dify/pulls?q=is%3Apr+author%3Aleslie2046+is%3Amerged)

### [Xinference](https://github.com/xorbitsai/inference)

* **Dynamic replica scaling [#5426](https://github.com/xorbitsai/inference/pull/5426) / [#5491](https://github.com/xorbitsai/inference/pull/5491)**: Add configurable scale-up and placement across multiple workers, with CPU/GPU allocation, failure rollback, and replica-state reconciliation.
* **Supervisor restart recovery [#4731](https://github.com/xorbitsai/inference/pull/4731) / [#5250](https://github.com/xorbitsai/inference/pull/5250)**: Reconnect workers and rebuild replica state after supervisor restarts, including recovery from stale supervisor references.
* **[OpenTelemetry integration #4666](https://github.com/xorbitsai/inference/pull/4666)**: Introduce optional OpenTelemetry instrumentation with a configurable OTLP endpoint for model-serving observability.

[All merged Xinference PRs](https://github.com/xorbitsai/inference/pulls?q=is%3Apr+author%3Aleslie2046+is%3Amerged)

### Other Contributions

* **[Dify Official Plugins](https://github.com/langgenius/dify-official-plugins)**: Provider and model updates for SiliconFlow, DeepSeek, Volcengine, Azure OpenAI, and tool-call message handling.
* **[Dify Plugin SDKs](https://github.com/langgenius/dify-plugin-sdks)** and **[Plugin Daemon](https://github.com/langgenius/dify-plugin-daemon)**: Runtime improvements around app context, persistence, and storage accounting.
* **[RAGFlow](https://github.com/infiniflow/ragflow)**: Model-provider additions and retrieval-system integration work.

## Languages and Tools

[![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/python/cpython)
[![Xinference](https://img.shields.io/badge/-Xinference-4B32C3?style=flat-square)](https://github.com/xorbitsai/inference)
[![Dify](https://img.shields.io/badge/-Dify-1C64F2?style=flat-square&logo=dify&logoColor=white)](https://github.com/langgenius/dify)
[![RAGFlow](https://img.shields.io/badge/-RAGFlow-FF5C35?style=flat-square)](https://github.com/infiniflow/ragflow)

[![Kaldi](https://img.shields.io/badge/-Kaldi-4B8BBE?style=flat-square)](https://github.com/kaldi-asr/kaldi)
[![sherpa-onnx](https://img.shields.io/badge/-sherpa--onnx-1F6FEB?style=flat-square)](https://github.com/k2-fsa/sherpa-onnx)
[![Ultralytics YOLO](https://img.shields.io/badge/-Ultralytics_YOLO-111F68?style=flat-square&logo=ultralytics&logoColor=white)](https://github.com/ultralytics/ultralytics)
[![PaddlePaddle](https://img.shields.io/badge/-PaddlePaddle-0062B0?style=flat-square&logo=paddlepaddle&logoColor=white)](https://github.com/PaddlePaddle/Paddle)
[![FunASR](https://img.shields.io/badge/-FunASR-5B45DE?style=flat-square)](https://github.com/modelscope/FunASR)

[![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/docker/docker-ce)
[![Langfuse](https://img.shields.io/badge/-Langfuse-000000?style=flat-square&logo=langfuse&logoColor=white)](https://github.com/langfuse/langfuse)
[![Grafana](https://img.shields.io/badge/-Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)](https://github.com/grafana/grafana)
[![RustFS](https://img.shields.io/badge/-RustFS-CE422B?style=flat-square)](https://github.com/rustfs/rustfs)

[![GitHub Roast score](https://ghfind.com/api/badge/leslie2046?lang=zh)](https://ghfind.com/u/leslie2046?ref=badge)
