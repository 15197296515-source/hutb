Examples
本目录包含 CARLA / HUTB Python API 的示例脚本。

运行任何示例之前，请先安装本目录的依赖，否则会报 ModuleNotFoundError: No module named 'pygame'。

1. 安装依赖
sh


python -m pip install -r PythonAPI/examples/requirements.txt
requirements.txt 中包含 pygame、numpy、matplotlib、open3d、networkx、Shapely、 Pillow、future，以及 invertedai（该包要求 Python >= 3.10）。

安装后验证：

sh


python -c "import pygame, numpy, matplotlib; print('ok')"
注意：python -m pip 与 python 必须指向同一个解释器，否则会出现"装好了却仍然导入失败"。

2. 启动模拟器
所有示例都需要先启动 CARLA / HUTB 服务端（默认端口 2000），再运行客户端脚本。

3. 常用示例
脚本	作用
manual_control.py	手动驾驶，可切换车辆与传感器
automatic_control.py	自动驾驶 + 手动接管
generate_traffic.py	批量生成交通流
dynamic_weather.py	动态天气与光照
bounding_boxes.py	绘制 3D 包围框
visualize_multiple_sensors.py	多传感器同步可视化
no_rendering_mode.py	无渲染模式（拓扑图视图）
open3d_lidar.py	用 Open3D 查看激光雷达点云
start_recording.py / start_replaying.py	录制与回放
在仓库根目录执行：

sh


python PythonAPI/examples/manual_control.py
python PythonAPI/examples/manual_control.py --filter walker.pedestrian.*
python PythonAPI/examples/generate_traffic.py -n 30
4. 子目录说明
目录	内容
air/	空地一体（无人机）相关示例
holoocean/	水下机器人（HoloOcean）相关示例
nvidia/	NVIDIA 相关示例
ros2/、rss/	ROS2 与 RSS 集成示例
5. 常见问题
ModuleNotFoundError: No module named 'pygame'

未安装示例依赖，执行：

sh


python -m pip install -r PythonAPI/examples/requirements.txt
RuntimeError: cannot import pygame, make sure pygame package is installed

同上的依赖缺失；若确认已安装仍报错，多半是包装到了另一个 Python 环境， 用 python -c "import sys; print(sys.executable)" 确认解释器路径。
