# BS Picture – AI models

Optional AI models used by [BS Picture](https://bs-picture.blogspot.com/), a fast photo viewer and editor for Windows ([Microsoft Store](https://apps.microsoft.com/detail/9MT1HL763JBP)).

The models are **not** included in the app. BS Picture downloads a model only the first time the user chooses the feature that needs it, checks its SHA-256 fingerprint, and then runs it locally on the PC with ONNX Runtime. Photos are never uploaded anywhere.

## Files

The files are published as assets of the [Releases](../../releases) of this repository.

| Release | File | Feature in BS Picture | Model | License | SHA-256 |
|---|---|---|---|---|---|
| `modelos-v2` (current) | `quitar_fondo_v2.onnx` (97 MB) | Remove background | BiRefNet lite (Swin-T), FP16 weights | MIT | `E811456A9088BFF0AFC5623845C54B1C9F020EFBA8F7CA8743539D0C30E954AC` |
| `modelos-v2` (current) | `borrar_objetos_v1.onnx` (101 MB) | Erase objects | LaMa (big-lama), FP16 weights | Apache License 2.0 | `6C8A0CC49421023B3D2A0712A19C33F44BD300A001373A6E88FF3C6E1656E0F3` |
| `modelos-v2` (current) | `colorear_v1.onnx` (110 MB) | Colorize black and white | DDColor tiny, FP16 weights | Apache License 2.0 | `36BA53ED2C91D9D192A5EF5A30B4623440930B0CE2C995B8FA493A55E4DACFF0` |
| `modelos-v2` (current) | `reparar_rayas_v1.onnx` (72 MB) | Repair scratches (finds them; the filling uses `borrar_objetos_v1.onnx`) | Scratch detection network of "Bringing Old Photos Back to Life", FP16 weights | MIT | `3EA1A382FB8660490F8EC44875ADAA51F563342F0B2AC203D98574AD5631528E` |
| `modelos-v2` (current) | `fondos_v2.zip` (53 MB) | New backgrounds (Backgrounds tab) | 104 images generated with Stable Diffusion XL 1.0 | see below | `86CBE49E880260AEF207C7747CA7CD6086F8370BD9C22461FAD66ADFB1978F6C` |
| `modelos-v2` (older app builds) | `fondos_v1.zip` (50 MB) | New backgrounds (Backgrounds tab) | 96 images generated with Stable Diffusion XL 1.0 | see below | `FF903D6609D7B66291F729F5CE850B60B04F4ABD9B111DAADD81DA4EB17E47AE` |
| `modelos-v2` (current) | `ampliar_rapido_v1.onnx` (5 MB) | Upscale (fast) | Real-ESRGAN realesr-general-x4v3 | BSD 3-Clause | `939255A67D1E756C01A4CFD23601459E3995AB43E1A462E544F73BCB84D9F28F` |
| `modelos-v2` (current) | `ampliar_calidad_v1.onnx` (32 MB) | Upscale (best quality) | Real-ESRGAN RealESRGAN_x4plus, FP16 weights | BSD 3-Clause | `BABB8B11E85FEB1BD181C6AB8A1E0426C4FD240FF0B2ABA5B4E9972394E71EC6` |
| `modelos-v1` (older app versions) | `quitar_fondo_v1.onnx` (86 MB) | Remove background | IS-Net general-use (DIS), FP16 | Apache License 2.0 | `3FD7A4F645A1D330CB275611196BBB3D6687935BC429CF7BC21BFB095236333E` |

## Credits and licenses

**BiRefNet** – Peng Zheng, Dehong Gao, Deng-Ping Fan, Li Liu, Jorma Laaksonen, Wanli Ouyang, Nicu Sebe. *Bilateral Reference for High-Resolution Dichotomous Image Segmentation*, CAAI Artificial Intelligence Research, 2024. https://github.com/ZhengPeng7/BiRefNet – MIT License (see `LICENSE-BiRefNet-MIT.txt` in the release).

**IS-Net (DIS)** – Xuebin Qin, Hang Dai, Xiaobin Hu, Deng-Ping Fan, Ling Shao, Luc Van Gool. *Highly Accurate Dichotomous Image Segmentation*, ECCV 2022. https://github.com/xuebinqin/DIS – Apache License 2.0 (see `LICENSE-IS-Net-Apache-2.0.txt` in the release).

The ONNX exports of the background models come from **rembg** by Daniel Gatis (https://github.com/danielgatis/rembg, MIT License).

**LaMa** – Roman Suvorov, Elizaveta Logacheva, Anton Mashikhin, Anastasia Remizova, Arsenii Ashukha, Aleksei Silvestrov, Naejin Kong, Harshith Goka, Kiwoong Park, Victor Lempitsky. *Resolution-robust Large Mask Inpainting with Fourier Convolutions*, WACV 2022. https://github.com/advimman/lama – Apache License 2.0 (see `LICENSE-LaMa-Apache-2.0.txt` in the release). The ONNX export comes from **Carve/LaMa-ONNX** (https://huggingface.co/Carve/LaMa-ONNX, Apache License 2.0).

**Real-ESRGAN** – Xintao Wang, Liangbin Xie, Chao Dong, Ying Shan. *Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data*, ICCVW 2021. https://github.com/xinntao/Real-ESRGAN – BSD 3-Clause License (see `LICENSE-Real-ESRGAN-BSD-3.txt` in the release).

**Bringing Old Photos Back to Life** (scratch detection) – Ziyu Wan, Bo Zhang, Dongdong Chen, Pan Zhang, Dong Chen, Jing Liao, Fang Wen. *Bringing Old Photos Back to Life*, CVPR 2020, and *Old Photo Restoration via Deep Latent Space Translation*, TPAMI 2022. https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life – Copyright (c) Microsoft Corporation, MIT License (see `LICENSE-BOPBTL-scratch-detection-MIT.txt`).

**DDColor** – Xiaoyang Kang, Tao Yang, Wenqi Ouyang, Peiran Ren, Lingzhi Li, Xuansong Xie. *DDColor: Towards Photo-Realistic Image Colorization via Dual Decoders*, ICCV 2023. https://github.com/piddnad/DDColor – Apache License 2.0 (see `LICENSE-DDColor-Apache-2.0.txt` in the release). The ONNX export of the `ddcolor_paper_tiny` checkpoint comes from **Qualcomm AI Hub Models** (https://huggingface.co/qualcomm/DDColor, Apache License 2.0).

**Themed backgrounds** (`fondos_v2.zip`, 104 images; `fondos_v1.zip`, the first 96) – original images (garden, beach, party, city, nature, sky, indoors, holidays, studio, abstract, wedding, graduation, sports, office, kids, travel) generated for BS Picture with **Stable Diffusion XL 1.0** by Stability AI (https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0, CreativeML Open RAIL++-M License, which places no restrictions on the use of generated images other than those of its use-based restrictions) and upscaled ×2 with Real-ESRGAN x4plus. They contain no people, logos or text. You may use them freely together with BS Picture.

**Modifications:**

- `reparar_rayas_v1.onnx`: built from the official `checkpoints/detection/FT_Epoch_latest.pt` (only the network weights; the training state was left out). Each batch normalization was folded into the preceding convolution and the weights are stored in FP16 and cast back to 32-bit when the model is loaded; computation stays in FP32. Its output matches the original PyTorch network. Input: grayscale photo scaled to -1..1 (shorter side 256 px, sides multiple of 16); output: logits (sigmoid ≥ 0.4 is a scratch).
- `colorear_v1.onnx`: the external weight file of the ONNX export was merged into a single file, with the weights stored in FP16 and cast back to 32-bit when the model is loaded; computation stays in FP32.
- `ampliar_rapido_v1.onnx` and `ampliar_calidad_v1.onnx`: converted to ONNX from the official `realesr-general-x4v3.pth` and `RealESRGAN_x4plus.pth` weights of the Real-ESRGAN releases (same networks, SRVGGNetCompact and RRDBNet; input RGB 0–1, output ×4). In `ampliar_calidad_v1.onnx` the weights are stored in FP16 and cast back to 32-bit when the model is loaded; computation stays in FP32.
- `borrar_objetos_v1.onnx`: the weights of the FP32 ONNX model are stored in half precision (FP16) and cast back to 32-bit when the model is loaded, so all computation stays in FP32 (a full FP16 conversion breaks the model's Fourier convolutions). The network was not otherwise changed.

- `quitar_fondo_v2.onnx`: in the ONNX export, every deformable convolution of the decoder had been expanded into gather/multiply operations that need about 6 GB of memory at 1024 × 1024. They were rewritten with standard operators that GPUs also support (DirectML): for each kernel position, `GridSample` (bilinear, zero padding, aligned corners) samples the input at the offset points, the result is multiplied by the modulation mask and by that position's slice of the weights as a 1 × 1 convolution, and the partial results plus the bias are summed. This gives the same output (average difference 0.002 of 255 on the mask) with much less memory. The weights are stored in half precision (FP16) and cast back to 32-bit when the model is loaded; computation stays in FP32. The weights were not otherwise changed.
- `quitar_fondo_v1.onnx`: the original FP32 ONNX model was converted to half precision (FP16) with ONNX Runtime's `float16` converter, keeping 32-bit inputs and outputs. The network and its weights were not otherwise changed.
