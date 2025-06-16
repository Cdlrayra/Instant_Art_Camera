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



graph TD
    A[开始] --> B{创建仿真环境};

    B --> C[使用 Isaac Gym 加载物理模型和资源];
    C --> D[定义时间步长和重力加速度];

    D --> E{配置任务和环境};
    E --> F[在 Legged Gym 中配置机器人模型、传感器和奖励函数];
    F --> G[初始化仿真环境和设置初始状态];

    G --> H{训练强化学习策略};
    H --> I[使用 rsl_rl (例如 PPO) 进行策略训练];
    I --> J[与仿真环境交互，收集观测、奖励和终止标志];
    J --> K[调整策略参数并优化控制策略];
    K --> L[记录关键信息并保存训练好的策略模型];

    L --> M{仿真测试与评估};
    M --> N[将训练好的策略模型加载到 pointfootMujoco 进行仿真测试];
    N --> O[观察机器人行为并记录数据];
    O --> P[评估策略有效性和鲁棒性];
    P --> Q[根据测试结果进行调整和优化];

    Q --> R{摇杆控制};
    R --> S[通过库发送控制指令];
    S --> T[驱动双点足机器人执行训练好的策略动作];

    T --> U[结束：机器人执行优化后的动作];

    subgraph 代码库关系
        IsaacGym[Isaac Gym]
        LeggedGym[Legged Gym]
        rsl_rl[rsl_rl]
        pointfootMujoco[pointfootMujoco]
        JoystickControl[摇杆控制模块]
    end

    C -- 使用 --> IsaacGym;
    F -- 使用 --> LeggedGym;
    I -- 使用 --> rsl_rl;
    N -- 使用 --> pointfootMujoco;
    S -- 使用 --> JoystickControl;
