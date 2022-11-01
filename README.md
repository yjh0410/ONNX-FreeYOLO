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
| FreeYOLO-Nano  |  416    |      |        |  |  |
| FreeYOLO-Tiny  |  416    |      |        |  |  |
| FreeYOLO-Large |  640    |   47.1   |   67.4     | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_large_opset_11.onnx) |  [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_large_opset_10.onnx) |
| FreeYOLO-Huge  |  640    |     |        |  |  |


## ONNXRuntime Demo

```shell
python3 onnx_inference.py --weight weights/onnx/11/yolo_free_large.onnx -i test_image.jpg -s 0.3 -size 640
```
Notes:
* --weight: your converted onnx model
* -i: input_image
* -s: score threshold for visualization.
* --img_size: should be consistent with the shape you used for onnx convertion.
