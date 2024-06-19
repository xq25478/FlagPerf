# 参评AI芯片信息

* 厂商：Ascend

## 服务器

* 产品名称：Atlas800T A2
* 产品型号：Atlas800T A2
* TDP：350W

# 所用服务器配置

* 服务器数量：1

## 服务器

* 单服务器内使用卡数：8
* 服务器型号：Atlas 800T A2训练服务器
* 操作系统版本：Ubuntu 22.04 LTS
* 操作系统内核：5.15.0-25-generic
* CPU：Kunpeng 920
* docker版本：此评测样例无需docker环境
* 内存：1TiB
* 服务器间AI芯片直连规格及带宽：此评测样例无需服务器间通信

# 评测结果

## 核心评测结果

| 评测项  | FP16算力测试值(8卡平均) | FP16算力标定值(8卡平均) | 测试标定比例(8卡平均) |
| ---- | ---------------- | ---------------- | ------------- |
| 评测结果 | 313.182TFLOPS | / | /       |

## 能耗监控结果

| 监控项  | 系统平均功耗 | 系统最大功耗 | 系统功耗标准差 | 单机TDP | 单卡平均功耗(8卡平均) | 单卡最大功耗(8卡最大) | 单卡功耗标准差(8卡平均) | 单卡TDP |
| ---- | ------------ | ------------ | ------------- | ----- | ------------- | ------------- | -------------- | ----- |
| 监控结果 | /      | /      | /        | /     | 364.513W | 364.900W        | 0.352W        | /  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度(平均) | 单卡平均显存占用(8卡平均) |
| ---- | --------------- | -------------- | ------------- | --------------- |
| 监控结果 | 8.236%        | 1.281%     | 65.500°C     | 89.537%    |