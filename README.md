# DiffTrans: Bilingual Text Difficulty-level Transfer System with Lexical Alignment and Visualization

##**Significance**

DiffTrans addresses a crucial gap in readability research by enabling bidirectional text difficulty-level transfer for both English and Chinese. Unlike traditional text simplification and paraphrasing approaches, it explicitly controls the difficulty level based on standardized proficiency scales (U.S. grade levels for English and HSK levels for Chinese) while preserving the original semantics. This allows the system to adapt texts for diverse audiences, such as helping readers with comprehension difficulties access complex information (e.g., medical or legal content) and assisting educators in preparing reading materials tailored to L1 and L2 learners at different proficiency levels. Furthermore, DiffTrans offers interpretable lexicon-level visualizations, making the rewriting process transparent and user-friendly.

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/English_platform.png)



##**Quick Start**

First, open the system link[](https://chineseedu.shuishan.net.cn:5009/) . The platform consists of two independent subsystems: the **English text rewriting system** running on port 5009, which uses a PPO model to transform English texts across different difficulty levels, and the **Chinese text rewriting system** running on port 5011, which adopts an SFT model to perform difficulty-level conversion for Chinese texts.

###**English Text Rewriting System**

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/run_English_rewrite.png)
In the English system, users can input an original sentence on the left, select a target difficulty level in the middle (**Elementary, Middle, High, or College**), click the **“Rewrite”** button, and view the rewritten sentence on the right. A set of example sentences with similar meanings but different difficulty levels is provided in the upper-right corner, which can be viewed by clicking the “**Example**” button. Users can then click the “**Analyze the text**” button to automatically assess both the original and rewritten sentences.

At the sentence level, the system applies the **Flesch Reading Ease (FRE)** metric to evaluate readability.
At the vocabulary level, the system tags each word according to the **CEFR (Common European Framework of Reference for Languages)** standard (A1–C2) and visualizes the vocabulary difficulty distribution. From the visualization, it can be observed that the lexicon extractor embedded in the model effectively controls text difficulty.



###**Chinese Text Rewriting System**

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/Chinese_platform.png)

Next, we switch to the Chinese text rewriting system (port 5011). Its interface provides several interactive buttons that support difficulty-controlled rewriting and analysis for Chinese texts. Users can enter a sentence on the left and select a target difficulty level (**HSK1–HSK6**, increasing in difficulty) in the control panel. By clicking the **“Rewrite”** button, the system generates the rewritten sentence on the right. The **“Analyze the text”** button evaluates the input or output sentence, showing its predicted difficulty level and vocabulary distribution based on the HSK vocabulary tiers. The **“Example”** button offers predefined sample sentences for quick testing, and the **“English Page”** button allows users to switch to the English text rewriting system.

![](https://github.com/TreeECNU/DiffTrans/blob/main/Figure/run_Chinese_rewrite.png)



##**Experiment Result**


| **Readability ($s_y$)**   | **FRE**  | **FREΔ ↓** | **RG-L ↑** | **H-Re ↑** |
|---------------------------|----------|-------------|------------|------------|
| **GPT-4o-mini**           |          |             |            |            |
| Elementary school(1)      | 70.96    | 19.04       | 54.12      | 0.24       |
| Middle school(2)          | 65.41    | 4.59        | 59.64      | 0.40       |
| High school(3)            | 60.73    | 10.73       | 62.54      | 0.30       |
| College(4)                | 47.42    | 27.42       | 60.92      | 0.14       |
| Average                   | -        | 15.44       | 59.31  | 0.27       |
| **SFT**                   |          |             |            |            |
| Elementary school(1)      | 73.97    | 16.03       | 61.63      | 0.29       |
| Middle school(2)          | 64.96    | 5.04        | 63.38      | 0.40       |
| High school(3)            | 51.89    | 1.89        | 61.91      | 0.38       |
| College(4)                | 32.27    | 12.27       | 55.22      | 0.29       |
| Average                   | -        | 8.81        | **60.54**  | 0.34       |
| **SFT + PPO ($R_{sent} + R_{cons}$)** |      |             |            |            |
| Elementary school(1)      | 78.77    | 11.23       | 58.62      | 0.38       |
| Middle school(2)          | 65.25    | 4.75        | 63.11      | 0.40       |
| High school(3)            | 50.70    | 0.70        | 61.27      | 0.38       |
| College(4)                | 28.87    | 8.87        | 53.06      | 0.32       |
| Average                   | -        | 6.39        | 59.02      | 0.37   |
| **SFT + PPO ($R_{lex} + R_{cons}$)** |       |             |            |            |
| Elementary school(1)      | 79.96    | 10.04       | 56.73      | 0.40       |
| Middle school(2)          | 64.65    | 5.35        | 61.65      | 0.40       |
| High school(3)            | 48.92    | 1.08        | 59.50      | 0.38       |
| College(4)                | 25.71    | 5.71        | 49.99      | 0.34       |
| Average                   | -        | **5.55**    | 56.97      | **0.38**   |
| **SFT + PPO ($R_{sent} + R_{lex} + R_{cons}$)** |  |             |            |            |
| Elementary school(1)      | 78.87    | 11.13       | 58.12      | 0.38       |
| Middle school(2)          | 65.25    | 4.75        | 62.69      | 0.40       |
| High school(3)            | 50.89    | 0.89        | 60.90      | 0.38       |
| College(4)                | 26.67    | 6.67        | 51.49      | 0.33       |
| Average                   | -        | 5.86    | 58.30      | 0.37   |
