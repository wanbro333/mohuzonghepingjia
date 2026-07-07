# 模糊综合评价 - 公司综合实力评价

对 a, b, c, d, e, f, g 七家公司进行模糊综合评价(Fuzzy Comprehensive Evaluation)，评价其综合实力并排序。

## 文件说明

| 文件 | 说明 |
|------|------|
| `fuzzy_evaluation.ipynb` | 主代码文件(Jupyter Notebook)，包含4个模块 |
| `company_data.xlsx` | 原始样本数据(7家公司 × 19个指标) |

## 评价指标体系

- **目标层(A)**: 公司综合实力
- **准则层(B)**: B1产品综合评价, B2成本费用, B3销售能力
- **指标层(C)**: 19个二级指标

## 代码模块

1. **数据处理** — 读取Excel, 梯形隶属函数, 隶属度矩阵
2. **权重确定** — AHP层次分析法(判断矩阵+一致性检验)
3. **模糊综合评价** — M(.,+)加权平均型两级模糊合成
4. **结果可视化** — 柱状图, 堆叠图, 雷达图, 对比图

## 运行方式

```bash
jupyter notebook fuzzy_evaluation.ipynb
```

或使用 VS Code / PyCharm 打开 .ipynb 文件运行。
