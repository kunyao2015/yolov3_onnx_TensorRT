# yolov3_onnx_TensorRT
python 下使用TensorRT加速yolov3运行

运行在python3下
在parser_cfg_file函数中，读取配置文件默认用二进制打开方式，可能是python2中的使用方法，在python3中，将读取方式由“rb”改成“r”
==> Context: Bad node spec: input: "085_convolutional_lrelu" input: "086_upsample_scale" output: "086_upsample" name: "086_upsample" op_type: "Upsample" attribute { name: "mode" s: "nearest" type: STRING }
这个报错信息，是由于onnx版本导致的，onnx==1.4版本可以正确执行
