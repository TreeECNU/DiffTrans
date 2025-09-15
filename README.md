# DiffTrans

| **Readability ($s_y$)**   | **FRE**  | **FRE$*\Delta$ $\downarrow$** | **RG-L $\uparrow$** | **H-Re $\uparrow$** |
|---------------------------|----------|-------------------------------|---------------------|---------------------|
| **GPT-4o-mini**           |          |                               |                     |                     |
| Elementary school(1)      | 70.96    | 19.04                         | 54.12               | 0.24                |
| Middle school(2)          | 65.41    | 4.59                          | 59.64               | 0.40                |
| High school(3)            | 60.73    | 10.73                         | 62.54               | 0.30                |
| College(4)                | 47.42    | 27.42                         | 60.92               | 0.14                |
| Average                   | -        | 15.44                         | __59.31__           | 0.27                |
| **SFT**                   |          |                               |                     |                     |
| Elementary school(1)      | 73.97    | 16.03                         | 61.63               | 0.29                |
| Middle school(2)          | 64.96    | 5.04                          | 63.38               | 0.40                |
| High school(3)            | 51.89    | 1.89                          | 61.91               | 0.38                |
| College(4)                | 32.27    | 12.27                         | 55.22               | 0.29                |
| Average                   | -        | 8.81                          | **60.54**           | 0.34                |
| **SFT + PPO ($\mathcal{R}*{\text{sent}} + \mathcal{R}*{\text{cons}}$)** |          |                               |                     |                     |
| Elementary school(1)      | 78.77    | 11.23                         | 58.62               | 0.38                |
| Middle school(2)          | 65.25    | 4.75                          | 63.11               | 0.40                |
| High school(3)            | 50.70    | 0.70                          | 61.27               | 0.38                |
| College(4)                | 28.87    | 8.87                          | 53.06               | 0.32                |
| Average                   | -        | 6.39                          | 59.02               | __0.37__            |
| **SFT + PPO ($\mathcal{R}*{\text{lex}} + \mathcal{R}*{\text{cons}}$)** |          |                               |                     |                     |
| Elementary school(1)      | 79.96    | 10.04                         | 56.73               | 0.40                |
| Middle school(2)          | 64.65    | 5.35                          | 61.65               | 0.40                |
| High school(3)            | 48.92    | 1.08                          | 59.50               | 0.38                |
| College(4)                | 25.71    | 5.71                          | 49.99               | 0.34                |
| Average                   | -        | **5.55**                      | 56.97               | **0.38**            |
| **SFT + PPO ($\mathcal{R}*{\text{sent}} + \mathcal{R}*{\text{lex}} + \mathcal{R}*{\text{cons}}$)** |          |                               |                     |                     |
| Elementary school(1)      | 78.87    | 11.13                         | 58.12               | 0.38                |
| Middle school(2)          | 65.25    | 4.75                          | 62.69               | 0.40                |
| High school(3)            | 50.89    | 0.89                          | 60.90               | 0.38                |
| College(4)                | 26.67    | 6.67                          | 51.49               | 0.33                |
| Average                   | -        | __5.86__                      | 58.30               | __0.37__            |
