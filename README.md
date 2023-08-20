# ControlNet-LLLite-ComfyUI

[ControlNet-LLLite](https://github.com/kohya-ss/sd-scripts/blob/sdxl/docs/train_lllite_README.md) の推論用のUIです。

ControlNet-LLLiteがそもそもきわめて実験的な実装のため、問題がいろいろあるかもしれません。

# Install

1. `custom_nodes`にcloneします。
2. `ControlNet-LLLite-ComfyUI/models` にモデルを入れます。サンプルは[こちら](https://huggingface.co/kohya-ss/controlnet-lllite/tree/main)からダウンロードできます。

# Usage

[サンプルのワークフロー](lllite_workflow.json)を読み込んでください。

# Hint

+ 生成画像サイズと制御用画像サイズが異なる場合はワークフローにあるように `image/upscaling/UpscaleImage` でリサイズしてください。
+ 通常の画像からCanny画像を作るには `image/preprocessors/Canny` のノードが使えます。

# Credits

laksjdjf 氏の [IPAdapter-ComfyUI](https://github.com/laksjdjf/IPAdapter-ComfyUI) を参考にしています。laksjdjf 氏に感謝します。
