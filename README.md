# JLC-Sky-Star-Foundation-Learning-Board-Kit | 嘉立创天空星筑基学习板示例代码

<div align="center">

👨‍💻 **项目维护**：[SoftheartedYYC](https://github.com/SoftheartedYYC) | 📺 **参考教程**：[哔哩哔哩-Alice_西风 蓝桥杯嵌入式](https://www.bilibili.com/video/BV1GhHrenEGt?vd_source=bed636796cb846140792266c553bead0) | 🔗 [官方 Wiki](https://wiki.lckfb.com/zh-hans/fdb/)

![天空星筑基学习板](https://image.lceda.cn/oshwhub/pullImage/88d4eed657f04a77ba5fc0a8cedc3bde.jpg)

**嘉立创天空星·筑基学习板 - 嵌入式全栈开发的理想演练场**

</div>

---

## 📘 项目简介

本仓库收录了**嘉立创天空星·筑基学习板**的示例代码和硬件资料。该项目基于 **Alice_西风（Bilibili）** 的 **STM32_Xifeng_V2** 框架构建，专为 STM32/GD32/CH32 微控制器学习与开发设计。

⚠️ **说明**：本项目代码为本人基于 STM32_Xifeng_V2 框架编写的示例工程，框架原作者为 B 站 UP 主 Alice_西风，特此感谢！

所有示例代码、文档和资源均免费提供，助力各级电子工程师加速技能成长！

🎓 **框架教程参考**：请前往 [哔哩哔哩-Alice_西风](https://www.bilibili.com/video/BV1GhHrenEGt?vd_source=bed636796cb846140792266c553bead0) 观看 STM32_Xifeng_V2 框架的详细讲解

---

## 🎯 项目特点

- 🚀 **标准框架**：基于 STM32_Xifeng_V2 框架构建，函数命名统一规范
- 🔄 **高可移植**：更换芯片时只调整底层 BSP 代码，业务逻辑完全不变
- 📦 **模块化**：每个外设功能独立封装，便于维护和复用
- 🤖 **AI 友好**：统一的函数名方便 AI 辅助开发和理解代码结构
- 💡 **初学者友好**：完整的注释和详细的文档说明
- 🆓 **完全免费**：所有资料开源，无版权限制

### 主要特性

| 特性 | 说明 |
|------|------|
| 🔧 **广泛兼容** | 兼容 STM32F407VET6/VGT6、GD32F407VET6、HC32F4A0PITB |
| 💡 **丰富 IO** | 提供 70+ 个可用 GPIO 引脚 |
| 🖥️ **显示支持** | SPI 接口 2.0 寸触摸屏扩展板 |
| 🔌 **调试接口** | 集成 DAPLink 调试器，支持下载调试 |
| ⚡ **多电压参考** | 三路电压基准可选，满足多种应用需求 |
| 📚 **完整文档** | 完善的在线文档和教程系列 |
| 🆓 **免费资源** | 所有资料、代码示例和文档免费提供 |

---

## 📂 目录结构

本仓库采用 **STM32_Xifeng_V2** 标准框架结构：

```
Project/
│
├── APP/                          # 应用程序层（业务逻辑）
│   ├── bsp_system.h             # 板级支持包（包含所有头文件）
│   ├── system.c/.h              # 系统基础函数
│   ├── scheduler.c/.h           # 任务调度器 - 时间片轮询机制
│   ├── filter.c/.h              # 滤波算法（中值、平均、滑动平均）
│   ├── ringbuffer.c/.h          # 环形缓冲区实现
│   ├── led_app.c/.h             # LED 应用模块
│   ├── key_app.c/.h             # 按键应用模块
│   ├── lcd.c/.h                 # LCD 显示驱动（底层）
│   ├── lcd_app.c/.h             # LCD 应用模块
│   ├── uart_app.c/.h            # 串口应用模块
│   ├── adc_app.c/.h             # ADC 应用模块
│   ├── rtc_app.c/.h             # RTC 实时时钟模块
│   ├── tim_app.c/.h             # 定时器应用模块
│   └── i2c_hal.c/.h             # I2C 硬件抽象层
│
├── Core/                         # 核心层（HAL 库配置）
│   ├── Inc/                     # 头文件目录
│   │   ├── main.h               # 主程序头文件
│   │   ├── gpio.h               # GPIO 配置（CubeMX 生成）
│   │   ├── adc.h                # ADC 配置
│   │   ├── dma.h                # DMA 配置
│   │   ├── rtc.h                # RTC 配置
│   │   ├── tim.h                # 定时器配置
│   │   ├── usart.h              # 串口配置
│   │
│   └── Src/                     # 源文件目录
│       ├── main.c               # 主程序实现
│       ├── gpio.c               # GPIO 初始化
│       ├── adc.c                # ADC 初始化
│       ├── dma.c                # DMA 初始化
│       ├── rtc.c                # RTC 初始化
│       ├── tim.c                # 定时器初始化
│       └── usart.c              # 串口初始化
│
├── Drivers/                     # 外设驱动库
│   ├── CMSIS/                   # CMSIS 核心库
│   └── STM32xx_HAL_Driver/      # ST HAL 库
│
├── MDK-ARM/                     # Keil 工程项目文件
└── README.md                     # 项目说明（本文件）
```

### 分层架构说明

| 层级 | 职责 | 配置内容 |
|------|------|----------|
| **APP** | 业务逻辑 | led_proc, key_proc, lcd_proc 等任务处理 |
| **Core** | 系统基础 | CubeMX 生成的 HAL 库初始化 |
| **Drivers** | 硬件驱动 | 由厂商提供，不建议修改 |

---

## 💻 开发环境

### 必需工具

选择您偏好的开发环境：

1. **Keil MDK-ARM v5** ⭐ 推荐
   - ARM Cortex-M 行业标准 IDE
   - 优秀的调试器集成
   - 提供免费评估版

2. **STM32CubeMX** ⭐ 推荐
   - ST 官方图形化配置工具
   - 自动 HAL 库初始化代码生成
   - 支持时钟、外设一键配置

3. **VS Code**
   - 现代化、轻量级、跨平台
   - 适合有经验的开发者
   - 需要额外配置

## 🚀 快速开始

### 前置条件

开始前，请确保您拥有：
- 天空星筑基学习板硬件套件
- 一台电脑（Windows/macOS/Linux）
- 已安装的 Git 工具
- 集成开发环境（Keil MDK-ARM v5、IAR 或 VS Code + PlatformIO）

#### 3. 编译烧录

对于每个示例：
1. 在 Keil 中打开 `.uvprojx` 项目文件
2. 根据实际硬件配置芯片型号
3. 编译项目（F7）
4. 连接 DAPLink 调试器
5. 下载固件到目标芯片

具体操作请参考各个示例的 README 文件。

## 🏆 致谢与版权说明

本项目的实现基于以下开源项目和资源：

### STM32_Xifeng_V2 框架
- **原作者**：Alice_西风（Bilibili UP 主）
- **教程链接**：[【蓝桥杯-嵌入式】无痛过渡STM32省国赛冲刺培训](https://www.bilibili.com/video/BV1GhHrenEGt?vd_source=bed636796cb846140792266c553bead0)
- **框架特点**：时间片轮询调度器、模块化设计、硬件抽象层
- **使用许可**：遵循原作者的开源协议

**特别说明**：
- ✅ 本项目代码为本人基于 Alice_西风原创的 STM32_Xifeng_V2 框架编写的示例工程，特别感谢其提供的优秀框架和详细教程
- ⚠️ 转载请注明出处和原作者信息

### 其他资源
- STM32CubeMX - STMicroelectronics 官方工具
- HAL 库 - STMicroelectronics
- GD32CubeProgrammer - GigaDevice

---

## 📖 文档与教程

### 在线资源

| 资源 | 链接 | 说明 |
|------|------|------|
| 📚 **官方 Wiki** | [立创·天空星筑基学习板](https://wiki.lckfb.com/zh-hans/fdb/) | 全面的教程和指南 |
| 🛒 **产品页面** | [OSHWhub](https://oshwhub.com/li-chuang-kai-faban/tian-kong-xing-zhu-ji-xue-xi-ban) | 购买和产品资料下载 |
| 📦 **硬件文件** | [OSHWhub](https://oshwhub.com/li-chuang-kai-fabu/tian-kong-xing-zhu-ji-xue-xi-ban/files) | 原理图、PCB 文件、物料清单 |
| 💻 **代码仓库** | [Gitee](https://gitee.com/lckfb) | 国内用户访问镜像站点 |

---

## 🤝 贡献指南

我们欢迎社区的贡献！以下是您可以提供帮助的方式：

### 贡献方式

1. **添加新示例**
   - 编写有完善文档的示例代码
   - 在适当位置包含电路图
   - 提交前充分测试

2. **完善文档**
   - 翻译教程到其他语言
   - 修正错别字和改进说明
   - 添加图表和插图

3. **报告问题**
   - 使用 GitHub Issues 报告 bug
   - 提供详细的复现步骤
   - 包含代码片段和错误信息

4. **功能请求**
   - 建议新的示例主题
   - 对现有内容提出改进建议
   - 通过评论投票支持功能请求

---

## 📄 开源协议

本仓库基于 **[Apache License 2.0](LICENSE)** 许可证发布。

部分硬件设计采用 **[Creative Commons Attribution-ShareAlike 4.0](https://creativecommons.org/licenses/by-sa/4.0/)** 开源协议发布。

使用时请遵守相关许可证要求。

---

## 🙏 致谢

特别感谢：

- **立创开发板 (LCKFB)** - 提供优秀的学习平台和硬件资源
- **STMicroelectronics** - 强大的 STM32 微控制器家族和 HAL 库
- **兆易创新 (GigaDevice)** - GD32 兼容替代方案
- **Alice_西风（Bilibili）** - STM32_Xifeng_V2 框架原创作者，提供优秀的学习框架和教程
- **立创开源硬件平台 (OSHWhub)** - 提供天空星学习板的硬件设计和资源共享
- **所有贡献者和社区成员** - 反馈、测试和支持

---

## 🔗 相关链接

- **官方文档中心**: [立创·天空星筑基学习板](https://wiki.lckfb.com/zh-hans/fdb/)
- **购买套件**: [立创开源硬件平台](https://oshwhub.com/li-chuang-kai-faban/tian-kong-xing-zhu-ji-xue-xi-ban)
- **硬件资源**: [原理图与 PCB](https://oshwhub.com/li-chuang-kai-fabu/tian-kong-xing-zhu-ji-xue-xi-ban/files)
- **立创商城**: [lckfb.com](https://lckfb.com/)
- **STM32_Xifeng_V2 框架教程**: [【蓝桥杯-嵌入式】无痛过渡STM32省国赛冲刺培训](https://www.bilibili.com/video/BV1GhHrenEGt?vd_source=bed636796cb846140792266c553bead0)

---

## ⭐ 支持本项目

如果您发现本仓库对您的学习或项目有所帮助，请给我们一个星！⭐

您的支持帮助我们持续改进和扩展示例集合，造福整个社区。

---

<div align="center">

### 📚 框架作者信息

**Alice_西风** | Bilibili UP 主 | 嵌入式开发者 | 米醋电子工作室掌舵人

🎬 **STM32_Xifeng_V2 框架教程**：[查看视频](https://www.bilibili.com/video/BV1GhHrenEGt?vd_source=bed636796cb846140792266c553bead0)

💡 **推荐理由**：
框架结构清晰，易于学习和移植

完整的注释和详细的文档说明

时间片轮询调度器设计巧妙

非常适合初学者入门和进阶

❤️ **感谢 Alice_西风提供的优秀框架！**

---

### 👤 项目作者

本项目代码由本人基于 STM32_Xifeng_V2 框架编写，旨在分享天空星学习板的使用经验和示例。

❤️ **为嵌入式系统社区用心打造**

---

最后更新：2026 年 8 月

*文档版本：1.0.0*

</div>
