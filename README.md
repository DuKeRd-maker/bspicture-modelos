# BS Picture – AI models

Optional AI models used by [BS Picture](https://bs-picture.blogspot.com/), a fast photo viewer and editor for Windows ([Microsoft Store](https://apps.microsoft.com/detail/9MT1HL763JBP)).

The models are **not** included in the app. BS Picture downloads a model only the first time the user chooses the feature that needs it, checks its SHA-256 fingerprint, and then runs it locally on the PC with ONNX Runtime. Photos are never uploaded anywhere.

## Files

The files are published as assets of the [Releases](../../releases) of this repository.

| File | Feature in BS Picture | Model | License | SHA-256 |
|---|---|---|---|---|
| `quitar_fondo_v1.onnx` (86 MB) | Remove background | IS-Net general-use (DIS), converted to FP16 | Apache License 2.0 | `3FD7A4F645A1D330CB275611196BBB3D6687935BC429CF7BC21BFB095236333E` |

## Credits and licenses

**IS-Net (DIS)** – Xuebin Qin, Hang Dai, Xiaobin Hu, Deng-Ping Fan, Ling Shao, Luc Van Gool. *Highly Accurate Dichotomous Image Segmentation*, ECCV 2022. https://github.com/xuebinqin/DIS – Apache License 2.0 (see `LICENSE-IS-Net-Apache-2.0.txt` in the release).

The ONNX export of the general-use weights comes from **rembg** by Daniel Gatis (https://github.com/danielgatis/rembg, MIT License).

**Modifications:** the original FP32 ONNX model was converted to half precision (FP16) with ONNX Runtime's `float16` converter, keeping 32-bit inputs and outputs. The network and its weights were not otherwise changed.
