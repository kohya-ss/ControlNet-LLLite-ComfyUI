# ControlNet-LLLite-ComfyUI

[ControlNet-LLLite](https://github.com/kohya-ss/sd-scripts/blob/sdxl/docs/train_lllite_README.md) の推論用のUIです。

ControlNet-LLLiteがそもそもきわめて実験的な実装のため、問題がいろいろあるかもしれません。

![image](https://github.com/kohya-ss/ControlNet-LLLite-ComfyUI/assets/52813779/ef2ea8d6-121b-48ea-b4b0-a41601dcd6f2)

# Install

1. `custom_nodes`にcloneします。
2. `ControlNet-LLLite-ComfyUI/models` にモデルを入れます。サンプルは[こちら](https://huggingface.co/kohya-ss/controlnet-lllite/tree/main)からダウンロードできます。

# Usage

[サンプルのワークフロー](lllite_workflow.json)を読み込んでください。

`strength`に効果の強さを指定できます。1.0でデフォルト、0.0で効果なしです。

`steps`と`start_percent`、`end_percent`で拡散ステップの一部にだけ効果を適用できます。`steps`にsamplerに指定したステップ数を指定し、`start_percent`と`end_percent`にそれぞれ開始と終了のステップを0から100で指定します。

（ノード内で全体のステップ数を確認できないためこのような仕様になっています。具体的な適用範囲はコンソール出力を確認してください。）

# Hint

+ 生成画像サイズと制御用画像サイズが異なる場合はワークフローにあるように `image/upscaling/UpscaleImage` でリサイズしてください。
+ 通常の画像からCanny画像を作るには `image/preprocessors/Canny` のノードが使えます。

# Credits

laksjdjf 氏の [IPAdapter-ComfyUI](https://github.com/laksjdjf/IPAdapter-ComfyUI) を参考にしています。laksjdjf 氏に感謝します。
