# Beijing-GaoKao-Math-Dataset 2021–2025
# Standardized Dataset for Beijing Gaokao Math & Mock Exams (2021–2025)
For evaluating mathematical reasoning in large language models

---

## Overview
This repository provides a **structured, labeled JSON dataset** of real and mock mathematics questions from the **Beijing National College Entrance Examination (Gaokao)** and senior‑high mock exams, covering **2021–2025**.

Each question includes:
- Original question text
- Standard answer
- Detailed step-by-step solution
- Official scoring criteria
- Annotated knowledge point & question type
- **Chinese–English bilingual text**

The dataset is built for **automated evaluation, training, and comparison** of large language models on mathematical problem‑solving, reasoning, modeling, proof, and novel‑definition understanding.

---

## Dataset Scope
- Time range: 2021 – 2025
- Region: Beijing, China
- Exam types:
  - Official Beijing Gaokao mathematics real questions
  - Beijing district‑level senior‑high 1st & 2nd mock exams
- Coverage: multiple‑choice, fill‑in‑the‑blank, and free‑response questions (including final problems and innovative novel‑definition questions)

---

## Data Fields
Each question entry includes:
1. `paperTitle` – exam paper title
2. `number` – question number
3. `chinese` – Chinese question stem and sub-questions
4. `english` – English translated question stem and sub-questions
5. `solutionSteps` – detailed solving steps
6. `standardAnswer` – standard answer (supports LaTeX)
7. `scoringCriteria` – official scoring rubric
8. `knowledgePoint` – knowledge category label
9. `questionType` – question type label

---

## Knowledge Point Annotation
| Label | Chinese Name | Description |
|-------|--------------|-------------|
| PROBABILITY_STATISTICS | 概率统计 | Probability & statistics: random events, distribution, expectation, variance, statistical inference |
| ANALYTIC_GEOMETRY | 解析几何 | Analytic geometry: conic sections, line‑curve relations, chord length, area |
| FUNCTIONS_DERIVATIVES | 函数与导数 | Functions & derivatives: monotonicity, extrema, tangents, inequality proof, zeros |
| SEQUENCES | 数列 | Sequences: arithmetic/geometric sequences, general term, summation, induction |
| NEW_DEFINITION_INNOVATION | 新定义与创新应用 | Novel definition & innovation: learning and applying new concepts on the fly |

---

## Question Type Annotation
| Label | Chinese Name | Description |
|-------|--------------|-------------|
| BASIC_CALCULATION | 基础计算题 | Basic computation: direct formula use, routine steps |
| CONTEXT_MODELING_AND_COMPARISON | 情境建模与比较题 | Contextual modeling & comparison: abstract modeling, inference |
| GEOMETRY_ALGEBRA_TRANSFORMATION | 几何代数转化题 | Geometry‑algebra conversion: coordinate system, equations, algebraic solving |
| DEDUCTIVE_PROOF | 推理论证题 | Deductive proof: derivative analysis, function construction, logical proof |
| COMPREHENSIVE_ANALYSIS_AND_INQUIRY | 综合分析与探究题 | Comprehensive analysis: case discussion, parameter ranges, zero counting |
| NEW_DEFINITION_DIRECT_APPLICATION | 新定义直接应用题 | Direct application of novel definitions |
| NEW_DEFINITION_PROOF_AND_INQUIRY | 新定义探究证明题 | Novel‑definition proof & inquiry: contradiction, induction, exhaustion |

---

## Data Format
All data is stored in **clean, unified JSON** for:
- Easy batch parsing (Python, Java, JS, etc.)
- Automated evaluation and scoring
- Filtering by knowledge point or question type
- LLM input/output alignment

---

## Example Entry (Excerpt)
```json
{
    "paperTitle": "2021 Beijing Dongcheng Senior Three First Mock Examination Mathematics",
    "questions": [
        {
            "number": 18,
            "chinese": {
                "stem": "小明同学两次测试成绩(满分100分)如表所示：...",
                "subQuestions": [
                    {
                        "question": "（Ⅰ）从小明同学第一次测试的科目中随机抽取1科，求该科成绩大于90分的概率；",
                        "solutionSteps": "1. 确定基本事件总数...",
                        "standardAnswer": "$\\frac{2}{3}$",
                        "scoringCriteria": "本问总分4分...",
                        "knowledgePoint": "PROBABILITY_STATISTICS",
                        "questionType": "BASIC_CALCULATION"
                    },
                    {
                        "question": "（Ⅱ）...求X的分布列和数学期望E(X)；",
                        "solutionSteps": "...",
                        "standardAnswer": "E(X) = $\\frac{7}{6}$",
                        "scoringCriteria": "...",
                        "knowledgePoint": "PROBABILITY_STATISTICS",
                        "questionType": "CONTEXT_MODELING_AND_COMPARISON"
                    },
                    {
                        "question": "（Ⅲ）判断上述观点是否正确？",
                        "solutionSteps": "...",
                        "standardAnswer": "不正确",
                        "scoringCriteria": "...",
                        "knowledgePoint": "PROBABILITY_STATISTICS",
                        "questionType": "CONTEXT_MODELING_AND_COMPARISON"
                    }
                ]
            },
            "english": {
                "stem": "Xiaoming's test scores (full score 100) in two tests are shown below:...",
                "subQuestions": [
                    // English questions, solutions, scoring, labels
                ]
            }
        }
    ]
}
```

---

## Typical Use Cases
1. Automated evaluation of **LLM Gaokao math problem‑solving ability**
2. **Benchmark testing** for mathematical reasoning, modeling, proof, and novel‑definition understanding
3. **Fine‑tuning & training** of math‑specialized large models
4. Statistical analysis of question distribution, difficulty, and scoring patterns
5. Development & validation of AI education and automatic grading systems

---

## Usage
1. Clone this repository to use the full dataset
2. JSON structure is consistent and directly parsable
3. Filter questions by `knowledgePoint` or `questionType`
4. Answers support LaTeX for formula rendering

---

## Contribution
Pull requests are welcome to:
- Add more years or regional exam questions
- Correct solutions or scoring criteria
- Improve labeling and formatting

---

