---
title: NeuTTS Air CPU API
emoji: 🗣️
colorFrom: indigo
colorTo: blue
sdk: gradio
sdk_version: 6.17.3
python_version: 3.12.12
app_file: app.py
suggested_hardware: cpu-basic
models:
  - neuphonic/neutts-air-q4-gguf
  - neuphonic/neucodec-onnx-decoder-int8
---

# NeuTTS Air free CPU profile

This profile runs Q4 GGUF on CPU Basic and exposes the Kokoro-compatible REST
routes. Set `API_PASSWORD` as a Space secret before using the API, and
`HF_TOKEN` with a token from an account granted access to the gated Neuphonic
repos; every Neuphonic repo is gated, so the engine downloads all model files
with it at startup (the preload step cannot authenticate).

The web interface is available at the Space root and requires the same password
before generation.
