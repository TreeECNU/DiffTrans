# DiffTrans: Bilingual Text Difficulty-level Transfer System with Lexicon Extraction and Visualization

## :sparkles: **Significance**

DiffTrans explores the task of text difficulty-level transfer in both English and Chinese, offering a system that can rewrite texts across different difficulty levels while preserving their semantics. Unlike traditional text simplification and paraphrasing approaches, it explicitly controls the difficulty level based on standardized proficiency scales (U.S. grade levels for English and HSK levels for Chinese) while preserving the original semantics. This allows the system to adapt texts for diverse audiences, such as helping readers with comprehension difficulties access complex information (e.g., medical or legal content) and assisting educators in preparing reading materials tailored to L1 and L2 learners at different proficiency levels. Furthermore, DiffTrans offers interpretable lexicon-level visualizations, making the rewriting process transparent and user-friendly.

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/English_platform.png)



## :rocket: **Quick Start**

First, open the system link [here](https://chineseedu.shuishan.net.cn:5009/). The platform consists of two independent subsystems: the **English text rewriting system** running on port 5009, and the **Chinese text rewriting system** running on port 5011.


### :wrench: **English Text Rewriting System**

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/run_English_rewrite.png)
In the English system, users can input an original sentence on the left, select a target difficulty level in the middle (**Elementary, Middle, High, or College**), click the **“Rewrite”** button, and view the rewritten sentence on the right. A set of example sentences with similar meanings but different difficulty levels is provided in the upper-right corner, which can be viewed by clicking the “**Example**” button. Users can then click the “**Analyze the text**” button to automatically assess both the original and rewritten sentences.

At the sentence level, the system applies the **Flesch Reading Ease (FRE)** metric to evaluate readability.
At the vocabulary level, the system tags each word according to the **CEFR (Common European Framework of Reference for Languages)** standard (A1–C2) and visualizes the vocabulary difficulty distribution. From the visualization, it can be observed that the lexicon extractor embedded in the model effectively controls text difficulty.



###  :wrench: **Chinese Text Rewriting System**

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/Chinese_platform.png)

Next, we switch to the Chinese text rewriting system (port 5011). Its interface provides several interactive buttons that support difficulty-controlled rewriting and analysis for Chinese texts. Users can enter a sentence on the left and select a target difficulty level (**HSK1–HSK6**, increasing in difficulty) in the control panel. By clicking the **“Rewrite”** button, the system generates the rewritten sentence on the right. The **“Analyze the text”** button evaluates the input or output sentence, showing its predicted difficulty level and vocabulary distribution based on the HSK vocabulary tiers. The **“Example”** button offers predefined sample sentences for quick testing, and the **“English Page”** button allows users to switch to the English text rewriting system.

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/run_Chinese_rewrite.png)



## :memo: **Experiment Result**


| **Readability ($s_y$)**   | **FRE**  | **FREΔ ↓** |
|---------------------------|----------|-------------|
| **SFT + PPO ($R_{lex} + R_{cons}$)** |
| Elementary school(1)      | 79.96    | 10.04       |
| Middle school(2)          | 64.65    | 5.35        |
| High school(3)            | 48.92    | 1.08        |
| College(4)                | 25.71    | 5.71        |
| Average                   | -        | **5.55**    |
