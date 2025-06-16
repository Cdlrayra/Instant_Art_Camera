# Instant_Art_Camera
This is a self-designed instant art camera system based on the Raspberry Pi. The camera system is capable of taking photos, printing black-and-white images based on the captured pictures, and generating poetry based on the visual content of the shots. Additionally, a simple graphical user interface has been developed for the system.

## The workflow of the camera system
* The process framework diagram of the entire workflow：
* ![image](https://github.com/user-attachments/assets/0b095bfc-f16f-4013-9081-583b622c1b7e)
* The processing workflow diagram for generating poetry based on the captured image:
* ![image](https://github.com/user-attachments/assets/de79295d-256f-4186-ab24-1d49cfe0c4f9)
* The implementation code for this processing workflow is referenced from the repository
* (link:https://github.com/bokito-studio/poetry-camera-rpi).
* The processing workflow diagram for generating and printing a sketch of the captured image:
* ![image](https://github.com/user-attachments/assets/3841a91d-c109-45a3-8e42-7d3cd31a7976)
* This section employs the U2Net network to achieve the entire functions. Firstly, the U2Net network, loaded with weights trained for salient object detection, is used to detect salient objects in the scene, significantly improving the print quality of the thermal printer. Subsequently, the U2Net network, loaded with weights capable of generating sketches, is utilized for further processing of the scene, further enhancing the print quality. The comparison of print effects is illustrated in the following figure:
* ![image](https://github.com/user-attachments/assets/7605a5c2-6f14-4aaf-852b-34040ec8b694)

## Materials required to implement this project and the achieved results:

Hardware: Power bank, Raspberry Pi, connectable camera, thermal printer, button， and thermal paper.

Physical diagram of the implemented camera system：
* ![image](https://github.com/user-attachments/assets/0fafbcd0-c187-4226-905b-e425479842e0)
* ![image](https://github.com/user-attachments/assets/fe1d01b7-61f5-4104-ad08-7e255d0bcaae)

* isaacgym/
├── assets/   # 存放各种模型、纹理等资源文件，用于在仿真环境中加载物体或场景
├── docker/   # 包含 Docker 配置文件，用于容器化部署 Isaac Gym
├── docs/   # 文档目录，通常包含用户手册、API 文档等
├── licenses/  # 存放许可证文件，确保代码使用的合法性和合规性
├── python/ 
│   ├── examples/   # 示例脚本目录：提供了一些使用 Isaac Gym 的典型用例
│   └── isaacgym/   # 核心目录
│       ├── _bindings/  # 绑定层，负责将底层 C++ 实现与 Python 接口进行桥接
│       │   ├── __init__.py  # 初始化文件，定义包的入口点
│       │   ├── carb.config.json  # 配置文件，可能用于设置Carbi的相关参数
│       │   ├── gymapi.py  # 提供对 Isaac Gym API 的访问接口，是用户与 Isaac Gym 进行交互的主要途径
│       │   ├── gymdeps.py  # 依赖管理模块，处理 Isaac Gym 所需的各种依赖项
│       │   ├── gymtorch.py  # 与 PyTorch 框架集成的模块，支持 GPU 加速计算
│       │   ├── gymutil.py  # 实用工具模块，提供一些常用的辅助函数，如数据处理、日志记录等
│       │   ├── rlgpu.py  # 针对强化学习任务的 GPU 支持模块，优化了大规模并行训练和高效的数据处理
│       │   ├── terrain_utils.py  # 地形生成工具模块，用于创建复杂的地形环境，满足不同研究需求
│       │   └── torch_utils.py  # PyTorch 工具模块，提供与 PyTorch 相关的辅助功能，如张量操作、模型保存与加载等
│       └── isaacgym.egg-info/  # Python 包的元数据信息，由 setup.py 在打包过程中自动生成，包含版本号、依赖关系等信息
├── LICENSE.txt
├── rlgpu_conda_env.yml
├── setup.py
├── create_conda_env_rlgpu.sh
└── README.txt
