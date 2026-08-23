---
title: NeuTTS Air ZeroGPU
emoji: ⚡
colorFrom: purple
colorTo: indigo
sdk: gradio
sdk_version: 6.17.3
python_version: 3.12.12
app_file: app.py
suggested_hardware: zero-a10g
models:
  - neuphonic/neutts-air
  - neuphonic/neucodec-onnx-decoder-int8
---

# NeuTTS Air on ZeroGPU

This profile uses the BF16 PyTorch NeuTTS Air backbone so Hugging Face can
allocate and release ZeroGPU around each queued inference call.

Select **ZeroGPU** in the Space hardware settings after uploading these files.
Authenticated API calls should pass a Hugging Face token so quota is charged to
the calling account. See `README.cpu.md` or the project documentation for the
free CPU REST deployment and the explanation of reference-based tone control.

Set `API_PASSWORD` as a Space secret, and `HF_TOKEN` with a token from an
account granted access to the gated Neuphonic repos; the engine downloads the
gated models with it at startup (the preload step cannot authenticate). The
visible web interface requires this password before generation. It is not an extra parameter on the
`synthesize_zerogpu(text, voice, speed)` API endpoint; API callers continue to
authenticate with their Hugging Face token.
