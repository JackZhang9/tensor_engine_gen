# tensor_engine_gen
安装tensorRT_,ONNX1.8,导出engine,
----------------------------------------------------------------------
D:\anaconda\setup\envs\torch7\python.exe D:/PycharmProjects/yolov5-7.0/export.py 
export: data=D:\PycharmProjects\yolov5-7.0\data\coco128.yaml, weights=D:\PycharmProjects\yolov5-7.0\yolov5s.pt, imgsz=[640, 640], batch_size=1, device=0, half=False, inplace=False, keras=False, optimize=False, int8=False, dynamic=False, simplify=False, opset=12, verbose=False, workspace=4, nms=False, agnostic_nms=False, topk_per_class=100, topk_all=100, iou_thres=0.45, conf_thres=0.25, include=['engine']
YOLOv5  2022-11-22 Python-3.8.15 torch-1.12.0 CUDA:0 (NVIDIA GeForce RTX 3060 Laptop GPU, 6144MiB)

Fusing layers... 
Model summary: 224 layers, 7266973 parameters, 0 gradients

PyTorch: starting from D:\PycharmProjects\yolov5-7.0\yolov5s.pt with output shape (1, 25200, 85) (14.1 MB)

ONNX: starting export with onnx 1.8.1...
ONNX: export success  2.3s, saved as D:\PycharmProjects\yolov5-7.0\yolov5s.onnx (28.1 MB)

TensorRT: starting export with TensorRT 8.4.2.4...
[03/30/2023-20:09:51] [TRT] [I] [MemUsageChange] Init CUDA: CPU +385, GPU +0, now: CPU 11975, GPU 2628 (MiB)
[03/30/2023-20:09:53] [TRT] [I] [MemUsageChange] Init builder kernel library: CPU +321, GPU +104, now: CPU 12356, GPU 2732 (MiB)
D:/PycharmProjects/yolov5-7.0/export.py:271: DeprecationWarning: Use set_memory_pool_limit instead.
  config.max_workspace_size = workspace * 1 << 30
[03/30/2023-20:09:54] [TRT] [I] ----------------------------------------------------------------
[03/30/2023-20:09:54] [TRT] [I] Input filename:   D:\PycharmProjects\yolov5-7.0\yolov5s.onnx
[03/30/2023-20:09:54] [TRT] [I] ONNX IR version:  0.0.7
[03/30/2023-20:09:54] [TRT] [I] Opset version:    12
[03/30/2023-20:09:54] [TRT] [I] Producer name:    pytorch
[03/30/2023-20:09:54] [TRT] [I] Producer version: 1.12.0
[03/30/2023-20:09:54] [TRT] [I] Domain:           
[03/30/2023-20:09:54] [TRT] [I] Model version:    0
[03/30/2023-20:09:54] [TRT] [I] Doc string:       
[03/30/2023-20:09:54] [TRT] [I] ----------------------------------------------------------------
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:369: Your ONNX model has been generated with INT64 weights, while TensorRT does not natively support INT64. Attempting to cast down to INT32.
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
[03/30/2023-20:09:54] [TRT] [W] onnx2trt_utils.cpp:395: One or more weights outside the range of INT32 was clamped
TensorRT: input "images" with shape(1, 3, 640, 640) DataType.FLOAT
TensorRT: output "output0" with shape(1, 25200, 85) DataType.FLOAT
TensorRT: building FP32 engine as D:\PycharmProjects\yolov5-7.0\yolov5s.engine
D:/PycharmProjects/yolov5-7.0/export.py:298: DeprecationWarning: Use build_serialized_network instead.
  with builder.build_engine(network, config) as engine, open(f, 'wb') as t:
[03/30/2023-20:09:54] [TRT] [I] [MemUsageChange] Init cuBLAS/cuBLASLt: CPU +0, GPU +8, now: CPU 12284, GPU 2740 (MiB)
[03/30/2023-20:09:54] [TRT] [I] [MemUsageChange] Init cuDNN: CPU +0, GPU +8, now: CPU 12284, GPU 2748 (MiB)
[03/30/2023-20:09:54] [TRT] [W] TensorRT was linked against cuDNN 8.4.1 but loaded cuDNN 8.3.2
[03/30/2023-20:09:54] [TRT] [I] Local timing cache in use. Profiling results in this builder pass will not be stored.
[03/30/2023-20:10:55] [TRT] [I] Some tactics do not have sufficient workspace memory to run. Increasing workspace size will enable more tactics, please check verbose output for requested sizes.
[03/30/2023-20:12:07] [TRT] [I] Detected 1 inputs and 4 output network tensors.
[03/30/2023-20:12:08] [TRT] [I] Total Host Persistent Memory: 125120
[03/30/2023-20:12:08] [TRT] [I] Total Device Persistent Memory: 849920
[03/30/2023-20:12:08] [TRT] [I] Total Scratch Memory: 3736064
[03/30/2023-20:12:08] [TRT] [I] [MemUsageStats] Peak memory usage of TRT CPU/GPU memory allocators: CPU 7 MiB, GPU 2186 MiB
[03/30/2023-20:12:08] [TRT] [I] [BlockAssignment] Algorithm ShiftNTopDown took 21.4205ms to assign 6 blocks to 152 nodes requiring 36044800 bytes.
[03/30/2023-20:12:08] [TRT] [I] Total Activation Memory: 36044800
[03/30/2023-20:12:08] [TRT] [I] [MemUsageChange] Init cuDNN: CPU +0, GPU +10, now: CPU 12128, GPU 2792 (MiB)
[03/30/2023-20:12:08] [TRT] [W] TensorRT was linked against cuDNN 8.4.1 but loaded cuDNN 8.3.2
[03/30/2023-20:12:08] [TRT] [I] [MemUsageChange] TensorRT-managed allocation in building engine: CPU +3, GPU +31, now: CPU 3, GPU 31 (MiB)
[03/30/2023-20:12:08] [TRT] [W] The getMaxBatchSize() function should not be used with an engine built from a network created with NetworkDefinitionCreationFlag::kEXPLICIT_BATCH flag. This function will always return 1.
[03/30/2023-20:12:08] [TRT] [W] The getMaxBatchSize() function should not be used with an engine built from a network created with NetworkDefinitionCreationFlag::kEXPLICIT_BATCH flag. This function will always return 1.
TensorRT: export success  140.4s, saved as D:\PycharmProjects\yolov5-7.0\yolov5s.engine (32.9 MB)

Export complete (143.7s)
Results saved to D:\PycharmProjects\yolov5-7.0
Detect:          python detect.py --weights D:\PycharmProjects\yolov5-7.0\yolov5s.engine 
Validate:        python val.py --weights D:\PycharmProjects\yolov5-7.0\yolov5s.engine 
PyTorch Hub:     model = torch.hub.load('ultralytics/yolov5', 'custom', 'D:\PycharmProjects\yolov5-7.0\yolov5s.engine')  
Visualize:       https://netron.app

Process finished with exit code 0
