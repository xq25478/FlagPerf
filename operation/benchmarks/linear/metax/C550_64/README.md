# 参评AI芯片信息

* 厂商：Metax


* 产品名称：C550
* 产品型号：曦云®C550 64G
* TDP：350W

# 所用服务器配置

* 服务器数量：1


* 单服务器内使用卡数：1
* 服务器型号：Nettrix X640 G40
* 操作系统版本：Ubuntu 20.04.1 LTS
* 操作系统内核：linux5.4.0-42-generic
* CPU：Intel(R) Xeon(R) Gold 6348-112core
* docker版本：27.0.3
* 内存：2.0TiB
* 服务器间AI芯片直连规格及带宽：此评测项不涉及服务期间AI芯片直连

# 算子库版本

https://github.com/FlagOpen/FlagGems. Commit ID:982781081f5d62856064ae986e8927a31e96c235

# 评测结果

## 核心评测结果

| 评测项  | 平均相对误差(with FP64-CPU) | TFLOPS(cpu wall clock) | TFLOPS(kernel clock) | FU(FLOPS Utilization)-cputime | FU-kerneltime |
| ---- | -------------- | -------------- | ------------ | ------ | ----- |
| flaggems |  1.771E-4   |       |        | 46.77% | 45.41% |
| nativetorch | 1.772E-4    |        |      | 70.28%      | 70.02%    |

说明：kerneltime采用triton.testing.do\_bench接口给出，准确度低于nsys等profiling工具

## 其他评测结果

| 评测项  | 相对误差(with FP64-CPU)标准差 | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- | ------------ |
| flaggems |  1.752E-6   |       |         |  |  |  |  |
| nativetorch | 2.510E-6    |        |         |  |  |  |  |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| flaggems监控结果 | 193.0W | 218.39W |  30.09W   | /     |     72.0W   |  72.0W     |    0.0W    | 350W  |
| nativetorch监控结果 | 207.29W | 245.18W | 15.85W    | /     | 72.0W       | 72.0W       | 0.0W        | 350W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| flaggems监控结果 |  3.089%   | 2.042% |   44.0°C   |     18.599%    |
| nativetorch监控结果 | 4.314%    | 1.991   | 44.0°C      | 18.599%        |