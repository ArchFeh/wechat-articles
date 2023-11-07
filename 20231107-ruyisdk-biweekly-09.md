# 如意SDK双周进展汇报  第009期·2023年11月07日

## 卷首语

天气渐冷，如意SDK双周进展已经来到了第9期。从本期开始，如意SDK双周进展将采用全新的内容组织形式，期望能给您带来更好的体验，成为您冬日里的一缕暖阳。

## 包管理器

项目地址：https://github.com/ruyisdk/ruyi

相比两周前，调整了一部分软件源的元数据格式，联网包管理器的功能也实现了大部分。
目前实现了以下的功能点：

* 二进制分发：可以打包为单个二进制可执行文件了。
  平台适配方面，我们为 amd64 架构适配了 Ubuntu 22.04、openEuler 23.09 两个发行版，
  为 riscv64 架构适配了 Debian 的 20231109 快照版本（预期在 Fedora 等发行版上也能正常运行）。
* 软件源相关：实现了软件源的同步、软件包的安装。
* 已安装包的管理：可以初步建立类似 Python virtualenv 用法的虚拟环境了：
  此做法可广泛兼容多种构建系统的现有集成方式，从而方便开发者使用。
  （目前虚拟环境内的命令符号链接仍待完善。）

除此之外，在 `ruyi` 的软件源相关功能基本完成后，也同步开始了测试工作。
目前与测试同学初步对接了 user story 的前半部分，待虚拟环境的符号链接功能完成后将继续下一步工作。

## IDE

前期RuyiIDE方面完成了基于Eclipse插件开发的技术学习。目前正在开展 Eclipse定制发行版的制作和安装程序打包工作，具体要求如下：

对标Eclipse IDE for Embedded C/C++ Developers包含的主要插件，基于Eclipse生成一个自定义的Eclipse Distribution，形成RuyiSDK IDE的初始打包过程/程序。要求首先能够产出功能等同于Eclipse IDE for Embedded C/C++ Developers的Linux环境下IDE安装程序，并在此基础上完成定制界面定制。

## GCC

继续开发RISC-V Profiles，Bitmanip/Scalar crypto intrinsic在工具链上的支持，开始准备向上游提交RVV 0.7&1.0的兼容性patch。完成了RVP向gcc13的porting工作，目前仍在review修改中。
