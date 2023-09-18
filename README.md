# ControlNet-LLLite-ComfyUI

日本語版ドキュメントは後半にあります。

This is a UI for inference of [ControlNet-LLLite](https://github.com/kohya-ss/sd-scripts/blob/sdxl/docs/train_lllite_README.md).

ControlNet-LLLite is an experimental implementation, so there may be some problems.

![image](https://github.com/kohya-ss/ControlNet-LLLite-ComfyUI/assets/52813779/ef2ea8d6-121b-48ea-b4b0-a41601dcd6f2)

## Installation

1. Clone this repository to `custom_nodes`.
2. Put ControlNet-LLLite models to `ControlNet-LLLite-ComfyUI/models`. You can download sample models from [here](https://huggingface.co/kohya-ss/controlnet-lllite/tree/main).

## Usage

Load [sample workflow](lllite_workflow.json).

You can specify the strength of the effect with `strength`. 1.0 is default, 0.0 is no effect.

You can apply only to some diffusion steps with `steps`, `start_percent`, and `end_percent`. Specify the number of steps specified in the sampler in `steps`, and specify the start and end steps from 0 to 100 in `start_percent` and `end_percent`, respectively.

(Because we cannot check the total number of steps in the node, this specification has been made. Please check the console output for the specific application range.)

## Tips

+ If the generated image size is different from the control image size, resize it with `image/upscaling/UpscaleImage` as shown in the workflow.

+ You can create a Canny image from a normal image with the `image/preprocessors/Canny` node.

## Acknowledgements

This repository is based on [IPAdapter-ComfyUI](https://github.com/laksjdjf/IPAdapter-ComfyUI) by laksjdjf. Thanks to laksjdjf.


# ControlNet-LLLite-ComfyUI：日本語版ドキュメント

[ControlNet-LLLite](https://github.com/kohya-ss/sd-scripts/blob/sdxl/docs/train_lllite_README.md) の推論用のUIです。

ControlNet-LLLiteがそもそもきわめて実験的な実装のため、問題がいろいろあるかもしれません。

![image](https://github.com/kohya-ss/ControlNet-LLLite-ComfyUI/assets/52813779/ef2ea8d6-121b-48ea-b4b0-a41601dcd6f2)

## インストール方法

1. `custom_nodes`にcloneします。
2. `ControlNet-LLLite-ComfyUI/models` にモデルを入れます。サンプルは[こちら](https://huggingface.co/kohya-ss/controlnet-lllite/tree/main)からダウンロードできます。

## 使い方

[サンプルのワークフロー](lllite_workflow.json)を読み込んでください。

`strength`に効果の強さを指定できます。1.0でデフォルト、0.0で効果なしです。

`steps`と`start_percent`、`end_percent`で拡散ステップの一部にだけ効果を適用できます。`steps`にsamplerに指定したステップ数を指定し、`start_percent`と`end_percent`にそれぞれ開始と終了のステップを0から100で指定します。

（ノード内で全体のステップ数を確認できないためこのような仕様になっています。具体的な適用範囲はコンソール出力を確認してください。）

## ヒント

+ 生成画像サイズと制御用画像サイズが異なる場合はワークフローにあるように `image/upscaling/UpscaleImage` でリサイズしてください。
+ 通常の画像からCanny画像を作るには `image/preprocessors/Canny` のノードが使えます。

## 謝辞

laksjdjf 氏の [IPAdapter-ComfyUI](https://github.com/laksjdjf/IPAdapter-ComfyUI) を参考にしています。laksjdjf 氏に感謝します。
