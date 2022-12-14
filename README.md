# ONNX-FreeYOLO

## Requirements
- We recommend you to use Anaconda to create a conda environment:
```Shell
conda create -n onnx_yolo python=3.6
```

- Then, activate the environment:
```Shell
conda activate onnx_yolo
```

- Requirements:
```Shell
pip install -r requirements.txt 
```

## Download FreeYOLO ONNX file
Main results on COCO-val:

| Model          |  Scale  |    AP    |    AP50    |  ONNX(opset=11)  |  ONNX(opset=10)  |
|----------------|---------|----------|------------|------------------|------------------|
| FreeYOLO-Nano  |  640    |   30.5   |   50.3     | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_nano_opset_11.onnx) | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_nano_opset_10.onnx) |
| FreeYOLO-Tiny  |  640    |   34.4   |   53.9     | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_tiny_opset_11.onnx) | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_tiny_opset_10.onnx) |
| FreeYOLO-Large |  640    |   48.3   |   68.5     | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_large_opset_11.onnx) | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_large_opset_10.onnx) |
| FreeYOLO-Huge  |  640    |      |        |  |  |


## ONNXRuntime Demo

For example:

```shell
python3 onnx_inference.py --weight weights/onnx/yolo_free_tiny_opset_11.onnx -i test_image.jpg -s 0.5 -size 640
```

Notes:
* --weight: your converted onnx model
* -i: input_image
* -s: score threshold for visualization.
* --img_size: should be consistent with the shape you used for onnx convertion.
