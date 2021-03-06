# 将Keras模型转成ONNX模型

## 安装keras2onnx库
```
pip install keras2onnx
```

## 转换命令
```
python convert2onnx.py xxx
```

可用参数如下:

- `--model_name` 字符串类型，代表测试时使用哪个模型，支持`enet`,`unet`,`segnet`,`fcn8`等多种模型，默认为`unet`。
- `--n_classes` 整型，代表分割图像中有几种类别的像素，默认为`2`。
- `--input_height`整型，代表要分割的图像需要`resize`的长，默认为`224`。
- `--input_width` 整型，代表要分割的图像需要`resize`的宽，默认为`224`。
- `--input_model` 字符串类型，代表模型的输入路径，如`../weights/unet.05.xxx.hdf5`。
- `--output_model` 字符串类型，代表转换出的onnx模型保存路径，默认`./unet.onnx`。

## 转换命令举例

```
python convert2onnx.py  --input_model ../weights/unet/unet.04-0.991749.hdf5 --output_model ./unet.onnx
```


# 将ONNX模型Simplify(非必须)

## 安装onnx-simplifier

```
pip install onnx-simplifier
```

## 转换命令举例

```
python -m onnxsim input_onnx_model output_onnx_model
```