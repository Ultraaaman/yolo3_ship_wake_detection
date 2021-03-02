这是一个舰船尾迹仿真及检测系统</br></br>

需要环境: `opencv-python`, `numpy` in `python 3.6`</br></br>

## 仿真
运行`kelvin.py`文件</br>
```Bash
python kelvin.py
```
可以使用不同的功能: </br>
`create_kelvin_SAR()` 仿真SAR图像</br>
`create_kelvin_simulation()` 坐标系仿真</br>
还有一些辅助功能, 按`分辨率`测距离, `m/s`转换为船速标准单位`节`等. </br></br>

## 尾迹检测
运行main.py文件
```Bash
python main.py ./image/test.png
```
`tv.py`实现了图像的`total variation`.</br>
通过对`total variation`处理后的图像做`hough变换`检测舰船尾迹.</br>
对检测出的尾迹线段做`nms`处理, 计算最长尾迹长度.</br>
根据公式`velocity = np.sqrt((0.06*wakeLength*9.81) / (2*np.pi))`进而计算舰船速度.</br>

