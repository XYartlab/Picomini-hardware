# Picomini-hardware
Open-source CNC controller hardware.
Picomini 开源运动控制板（硬件仓库）
本仓库包含 Picomini 开源运动控制板的硬件设计与使用说明文档。控制板主要面向 grblHAL
运动控制固件设计，也可用于 CNC、雕刻、激光及自动化设备。
项目概述
Picomini 是一款基于 RP2040 的多轴运动控制板，提供完整的步进电机脉冲输出、主轴控制、输入输
出隔离以及扩展接口。本仓库仅包含硬件相关内容，不包含固件或上位机软件。
主要特性
◆ 兼容 Ultimate Pico（RP2040）
◆ 4 轴最高 200 kHz 脉冲输出
◆ 主轴 0–10V 模拟量速度控制（PWM 放大）
◆ 主轴 PWM / EN / DIR 同时支持继电器输出
◆ 8 路光耦隔离输入，支持 5V / 12V / 24V
◆ 6 路继电器输出，支持冷却、喷雾、照明等
◆ USB 或以太网通信（W5100S / W5500）
◆ 1 路 UART / I2C 扩展接口
适用 PCB 版本
◆ v1.00eth
◆ v1.10eth
不同 PCB 版本在 IO 定义和供电方式上存在差异，使用前请参考用户手册对比说明。
供电说明
◆ 主电源：12V（必需，用于 0–10V 输出与继电器）
◆ USB：用于通信，不建议作为唯一供电
◆ 输入供电与输出供电默认隔离，可按需共地（不推荐）
主轴控制
◆ 0–10V 输出未隔离，建议使用屏蔽线
◆ EN / DIR 用于主轴启停与方向控制
◆ grblHAL 逻辑下，正反转时 EN 始终保持有效
◆ 实际应用中推荐仅使用正转（M3）
输入接口
◆ 默认常闭（NC）逻辑，带状态指示灯
◆支持两线机械开关和三线接近开关
◆ 三线接近开关接线：棕=i12V，蓝=IG，黑=IO
◆ 急停输入为必接项
输出与继电器
◆ 推荐使用光耦隔离继电器模块
◆ 继电器输入电压需与模块规格匹配
◆ 可通过 M7 / M8 / M62–M65 指令控制输出
调试与上位机
◆ 调试软件：ioSender
◆ 推荐上位机：ncSender（支持 Web 界面）
 通过 $pins 命令查看 IO 映射
License
本项目硬件文档采用 Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC
BY-NC-SA 4.0) 协议发布。
允许非商业使用、修改与再发布，衍生作品需采用相同协议并署名。
版权声明
Copyright © 2025 XYartlab
本项目为开源硬件设计文档，不提供任何形式的担保
## License 
This hardware design is licensed under CC BY-NC SA 4.0.
