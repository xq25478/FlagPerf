Ascend GPU配置与运行信息参考

#### 环境配置
- ##### Atlas 800T A2硬件环境
    - 机器型号: Atlas 800T A2
    - 加速卡型号: Atlas 800T A2
    - CPU型号: KunPeng 920
    - 多机网络类型、带宽: 此评测样例无需多机网络

- ##### Atlas 800T A2软件环境

   - OS版本：Ubuntu 22.04 LTS
   - OS kernel版本: 5.15.0-25-generic     
   - 加速卡驱动版本：24.1.rc2
   - Docker 版本：此评测样例无需docker环境
   - 训练框架版本：deepspeed 0.13.1

### 运行情况

* 通用指标

| 指标名称       | 指标值                  | 特殊说明                                    |
| -------------- | ----------------------- | ------------------------------------------- |
| 任务类别       | 自然语言编码            |                                             |
| 模型           | bert-large-uncased      |                                             |
| 数据集         | Wikipedia               |                                             |
| 数据精度       | precision,见“性能指标”  | 可选fp32/amp/fp16                           |
| 超参修改       | fix_hp,见“性能指标”     | 跑满硬件设备评测吞吐量所需特殊超参          |
| 硬件设备简称   | nvidia A100             |                                             |
| 硬件存储使用   | mem,见“性能指标”        | 通常称为“显存”,单位为GiB                    |
| 端到端时间     | e2e_time,见“性能指标”   | 总时间+Perf初始化等时间                     |
| 总吞吐量       | p_whole,见“性能指标”    | 实际训练序列数除以总时间(performance_whole) |
| 训练吞吐量     | p_train,见“性能指标”    | 不包含每个epoch末尾的评估部分耗时           |
| **计算吞吐量** | **p_core,见“性能指标”** | 不包含数据IO部分的耗时                      |
| 训练结果       | acc,见“性能指标”        | masked_lm任务准确率(实际/目标)              |
| 额外修改项     | fp16实现方式            | nvidia使用1+8+7格式(bf16)来实现16位浮点数   |

* 性能指标

| 配置                | precision | fix_hp           | e2e_time | p_whole | p_train | p_core | acc         | mem     |
| ------------------- | --------- | ---------------- | -------- | ------- | ------- | ------ | ----------- | ------- |
| A100单机8卡（1x8）  | fp32      | bs=12            |          |         |         |        | 0.657/0.655 | 35.5/64 |
| A100单机8卡（1x8）  | amp       | bs=20,lr=5e-5    | 1708     | 363.2   | 386     | 394.6  | 0.658/0.655 | 38.9/64 |
| A100单机8卡（1x8）  | bf16      | bs=32,lr=1e-4    | 1144.7   | 544.5   | 569.5   | 592.3  | 0.647/0.655 | 37.7/64 |
| A100单机单卡（1x1） | fp32      | bs=12,lr=6.25e-6 |          |         |         |        | 0.655/0.655 | 40.8/64 |

