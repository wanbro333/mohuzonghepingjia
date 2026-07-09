# 模糊综合评价 —— 公司综合实力评价

对 a, b, c, d, e, f, g 七家公司进行模糊综合评价（Fuzzy Comprehensive Evaluation），评价其综合实力并排序。

## 项目结构

```
mohuzonhepingjia/
├── fuzzy_evaluation.ipynb           # 主代码（Jupyter Notebook，4 模块）
├── company_data.xlsx                # 样本数据（7 公司 × 19 指标，3 个工作表）
├── README.md                        # 项目说明
├── .gitignore
│
├── charts/                          # 可视化图表
│   ├── score_ranking.png            #   综合得分排序柱状图
│   ├── grade_distribution.png       #   评价等级隶属度堆叠图
│   ├── radar_chart.png              #   一级指标雷达图
│   ├── dimension_comparison.png     #   一级指标分组对比柱状图
│   └── weight_distribution.png      #   19 指标权重分布水平条形图
│
├── docs/                            # 论文与方法指南
│   ├── paper.tex                    #   学术论文 LaTeX 源文件
│   ├── paper.pdf                    #   学术论文 PDF（18 页）
│   ├── 模糊综合评价模型建立方法.md   #   方法指南 Markdown 版
│   ├── 模糊综合评价模型建立方法.tex  #   方法指南 LaTeX 版（学习笔记格式）
│   └── 模糊综合评价模型建立方法.pdf  #   方法指南 PDF（19 页，含代码+流程图）
│
└── src/                             # 辅助脚本
    └── build_nb.py                  #   Notebook 构建脚本
```

## 评价指标体系

- **目标层 (A)**：公司综合实力
- **准则层 (B)**：B1 产品综合评价，B2 成本费用，B3 销售能力
- **指标层 (C)**：19 个二级指标（偏大型 9 个 + 偏小型 8 个 + 中间型 2 个）

## 代码模块

1. **数据处理** — 读取 Excel，梯形隶属函数，隶属度矩阵
2. **权重确定** — AHP 层次分析法（判断矩阵 + 一致性检验）
3. **模糊综合评价** — M(·,⊕) 加权平均型两级模糊合成
4. **结果可视化** — 柱状图，堆叠图，雷达图，对比图，权重图

## 运行方式

```bash
jupyter notebook fuzzy_evaluation.ipynb
```

或使用 VS Code / PyCharm 打开 .ipynb 文件运行。

## LaTeX 论文编译

```bash
cd docs
xelatex paper.tex
xelatex paper.tex     # 两次编译以解析交叉引用
```

## 方法学习

如果你是数学建模初学者，推荐按以下顺序阅读：

1. 先打开 `fuzzy_evaluation.ipynb` 跑一遍代码，观察输出
2. 阅读 `docs/模糊综合评价模型建立方法.md` 或 `docs/模糊综合评价模型建立方法.pdf`，理解每个步骤的原理
3. 阅读 `docs/paper.pdf`，学习如何将方法写成论文
