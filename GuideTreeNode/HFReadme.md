# HF Projects

# 说明
本仓库的作用是对短波通信其他仓库的一些说明。
主要保存一些自己的版本，和一些没有放于Team仓库的工程。

## 主程序
- [主程序(C语言)](https://github.com/SEU-HF-TEAM/audio_test)
	、[我的版本](https://github.com/niyilu45/projects-HFProgram-audio_test)
- [主程序(MATLAB)](https://github.com/SEU-HF-TEAM/HFSystemSim)
	、[我的版本](https://github.com/niyilu45/projects-HFProgram-HFSystemSim)
- [不完整主程序(VS)](https://github.com/SEU-HF-TEAM/AudioTestSimVS):只包含接收端


## 模块测试程序
该部分程序主要为主程序中的某一部分功能的单独测试程序：

- [LDPC编码(高斯消元)](https://github.com/SEU-HF-TEAM/LDPC-Encoder-GaussElimination)
	、[我的版本](https://github.com/niyilu45/LDPC-Encoder-GaussElimination)
- [LDPC编码(解方程)](https://github.com/SEU-HF-TEAM/LDPC-Encoder-SolveEquations)
	、[我的版本](https://github.com/niyilu45/LDPC-Encoder-SolveEquations)
- [同步性能测试](https://github.com/SEU-HF-TEAM/SyncPerformence)
	、[我的版本](https://github.com/niyilu45/projects-HFProgram-SyncPerformance)
- [RM码性能测试](https://github.com/SEU-HF-TEAM/ReedMuller-Test)
- [最低限度](https://github.com/SEU-HF-TEAM/MinimunSim)
- [加密程序](https://github.com/SEU-HF-TEAM/cpuEncrypt_test)

## 工具程序
该部分程序主要用于配合调试：
- [5G LDPC矩阵生成](https://github.com/SEU-HF-TEAM/Gen-5G-LDPC-H)
- [裁剪Raw文件](https://github.com/SEU-HF-TEAM/CutRawFile)
	、[我的版本](https://github.com/niyilu45/projects-HFProgram-CutRawFile)
- [简易的UDP传输程序](https://github.com/SEU-HF-TEAM/EasyUDPClient)
	、[我的版本](https://github.com/niyilu45/projects-HFProgram-EasyUDPClient)
- [串口程序](https://github.com/SEU-HF-TEAM/User_Interface_NoRts)
- [延迟测试程序](https://github.com/SEU-HF-TEAM/DelayTest)

## 文档
- [主程序(C语言)设计文档](https://github.com/SEU-HF-TEAM/audio_test-Doc)
	、[我的版本](https://github.com/niyilu45/projects-HFProgram-audio_test-Doc)
- [主程序(C语言)思维导图](https://github.com/SEU-HF-TEAM/HFProjectsStart/blob/master/audio_test%E5%AF%BC%E5%9B%BE.xmind)
- [主程序(MATLAB)设计文档](https://github.com/SEU-HF-TEAM/HFSystemSim-Doc)
- [ARM程序软件操作说明书以及性能测试样例说明文档](https://github.com/SEU-HF-TEAM/SoftwareOperationManual-Doc)
- [加密程序说明文档](https://github.com/SEU-HF-TEAM/cpuEncrypt_test-Doc)
- [Mex文件调试经验](https://github.com/SEU-HF-TEAM/MexDebugging-Doc)
- [三次样条插值文档](https://github.com/SEU-HF-TEAM/CubicSplineInterpolation-Doc)
- [RM码文档](https://github.com/SEU-HF-TEAM/ReedMuller-Test-Doc)
- [板子资料和信道模拟器](https://github.com/SEU-HF-TEAM/BoardInformationAndChannelSimulator)

## 未放置于Team的仓库
- [同步方法进一步研究](https://github.com/niyilu45/projects-HFProgram-SyncResearch)
- [寻找较优的m序列对](https://github.com/niyilu45/projects-HFProgram-FindBestMseqPair)

## 进一步的优化方向
该部分表示可以进一步进行优化的地方，
这部分内容在C程序的设计文档中有所提及。

- 在进行同步频偏试探计算相关值的时候，
	不再对接收序列进行频偏补偿再做相关，
	而是改为对本地序列进行补偿，
	并存下来，
	可以减少实际运行过程中的运算量。
- 粗同步在计算相关值门限的时候，
	可以采用单调队列的方式对滑动窗中的最大值进行存储,
	可以参考[LeeCode 239题 滑动窗口的最大值](https://leetcode-cn.com/problems/sliding-window-maximum/)

- 接收端的采样率转换函数可以加入步进来动态调整输出采样率，
	以抵抗由于晶振偏差所导致的符号定时位置变化的问题
- 均衡改成双倍采样(仿真已完成)
- 大迭代，均衡器需要简化或者修改
- 考虑修改导频格式，进一步降低导频长度（信道延迟短时性能增益比较明显）
- 改用性能更好的编码（考虑polar或者其它）
- 根据信号幅度小时删除或者调整软量提高编码增益
- 考虑采用喷泉码（复杂度高，有tradeoff，只在衰落下性能好）
- 自适应选频（需要电台配合）
-线（需要天线和电台配合，或者多部电台，多个天线）
- 多频分集（多部电台）
- ARM试试定点数计算会不会比double的计算快一些


