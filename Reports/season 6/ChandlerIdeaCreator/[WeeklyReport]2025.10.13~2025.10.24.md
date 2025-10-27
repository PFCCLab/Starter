### 姓名

钱畅阳

### 开发中的快乐开源任务

*   【热身打卡】开发框架，从编译 paddle 开始

### 本双周工作

本双周的核心工作是深度参与并最终成功完成了“从编译 paddle 开始”的热身打卡任务。这个过程虽然充满挑战，但也带来了巨大的收获，让我对大型深度学习框架的构建、环境依赖、问题排查有了极为深刻的理解。

1.  **环境搭建与初次编译尝试**
    *   根据任务指南，选择使用 Docker 搭建编译环境，成功拉取了官方开发镜像。
    *   在容器内克隆了 PaddlePaddle 的最新 `develop` 分支代码，并创建 `build` 目录。
    *   初次尝试 `cmake` 配置时，遇到了 Python 版本不匹配的问题 (要求 `>3.9` 而非 `3.8`)，通过修改 `-DPY_VERSION` 参数为 `3.10` 成功解决。
    *   初次执行 `make` 编译，在耗时近一小时后，于链接阶段遇到了 `undefined reference to pir::detail::TypeIdResolver` 的错误。

2.  **系统性问题诊断与环境重构（本双周核心难点与收获）**
    *   在尝试修复链接错误的过程中，多次遭遇了 Docker 容器崩溃 (`unexpected EOF`) 的问题，导致编译中断。
    *   通过一系列排查，最终定位到问题的根源在于本地 Docker Desktop 使用了陈旧的 Hyper-V 后端，而非高性能的 WSL 2 后端，导致资源管理不稳定。
    *   根据诊断结果，对本地开发环境进行了彻底重构：
        1.  以管理员权限开启了 Windows 的 `VirtualMachinePlatform` 和 `Microsoft-Windows-Subsystem-Linux` 功能。
        2.  成功安装并配置了 WSL 2 作为默认版本。
        3.  从 Microsoft Store 安装了 Ubuntu 发行版，并完成了初始化。
        4.  重新配置 Docker Desktop，使其后端切换到稳定、高效的 WSL 2，并成功启用了与 Ubuntu 的集成。

3.  **最终编译与任务完成**
    *   在全新的 WSL 2 环境下，同步了上游最新的 `develop` 分支代码，并彻底清除了旧的 `build` 目录。
    *   重新配置 `cmake` 并执行 `make`。在最后打包阶段遇到了 `Missing build dependency: networkx` 的 Python 依赖问题。
    *   通过 `pip install -r python/requirements.txt` 补全依赖后，成功完成了全部编译工作。
    *   最终，顺利完成了任务要求的所有后续步骤：
        *   体验并记录了三次二次编译（修改头文件、实现文件、Python文件）的时间差异。
        *   成功将自己编译的 `.whl` 包安装到环境中，并通过了 `run_check()` 验证。
        *   成功运行了指定的 `ctest` 单元测试，证明编译产物功能完备。

### 问题疑惑与解答

*   **问题 a？** 为什么 `make` 过程中 Docker 容器会反复崩溃，提示 `unexpected EOF`？
    *   **答：** 根源在于 Docker 使用了旧的 Hyper-V 后端，在高强度的并行编译下资源不稳定。通过将后端切换到现代化的 WSL 2，并为其分配合理的内存（通过 `.wslconfig` 文件），问题得到了彻底解决。

*   **问题 b？** 为什么编译到最后 `[100%]` 时，会因为缺少 `networkx` 而失败？
    *   **答：** 因为 PaddlePaddle 的打包脚本 (`setup.py`) 依赖一些 Python 包来完成工作。虽然 C++ 编译已全部完成，但 Python 依赖的缺失导致最后一步打包失败。这提示我在 `make` 之前，就应该先完整地安装 `python/requirements.txt` 中的所有依赖。

### 未来双周计划

1.  **巩固学习成果**：重新梳理本次编译过程，深入理解 `cmake`、`make` 的工作流，以及 `ccache` 缓存机制在增量编译中的作用。
2.  **熟悉源码结构**：在本地IDE中配置好编译完成的 PaddlePaddle 源码，学习和追踪一个简单 OP（如 `scale`）从上层到底层实现的完整调用链路。
3.  **认领新任务**：从启航计划任务列表中，做Stable-Diffusion 训练推理，为社区做贡献。