# 参评AI芯片信息

* 厂商：Nvidia

* 产品名称：A100
* 产品型号：A100-40GiB-SXM
* TDP：400W

# 所用服务器配置

* 服务器数量：1
* 单服务器内使用卡数: 1
* 服务器型号：DGX A100
* 操作系统版本：Ubuntu 20.04.4 LTS
* 操作系统内核：linux5.4.0-113
* CPU：AMD EPYC7742-64core
* docker版本：20.10.16
* 内存：1TiB
* 服务器间AI芯片直连规格及带宽：此评测项不涉及服务期间AI芯片直连

# 算子库版本

https://github.com/FlagOpen/FlagGems. Commit ID: 801377f03ba4649bc2d839ff34e38be66ee8a633

# 评测结果

## 核心评测结果

| 评测项  | correctness | TFLOPS(cpu wall clock) | TFLOPS(kernel clock) | FU(FLOPS Utilization)-cputime | FU-kerneltime |
| ---- | -------------- | -------------- | ------------ | ------ | ----- |
| flaggems | : False    | 0.28TFLOPS       | 0.28TFLOPS        | 0.09% | 0.09% |
| nativetorch | : False    | 0.33TFLOPS      | 0.33TFLOPS      | 0.11%      | 0.11%    |

## 其他评测结果

| 评测项  | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- | 
| flaggems | 3770.39us       | 3776.51us        | 265.22op/s | 264.79op/s | 1753860.08us | 3873.11us |
| nativetorch | 3249.78us       | 3254.27us        | 307.71op/s | 307.29op/s | 16870.64us | 3264.82us |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| nativetorch监控结果 | 1638.0W | 1794.0W | 156.0W   | /     | 359.33W       | 363.0W      | 5.43W        | 400W  |
| flaggems监控结果 | 1638.0W | 1794.0W | 156.0W   | /     | 386.53W       | 392.0W      | 7.37W        | 400W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| nativetorch监控结果 | 0.744%    | 2.308%   | 54.8°C       | 17.394%        |
| flaggems监控结果 | 0.641%    | 2.307%   | 62.28°C       | 17.212%        |
