---
license: mit
Programminglanguage: "Java"
version: "N/A"
Date: "May 2019 paper release date for https://arxiv.org/pdf/1812.08693.pdf"
Contaminated: "Very Likely"
Size: "Standard Tokenizer "
---

### Dataset is imported from CodeXGLUE and pre-processed using their script.

# Where to find in Semeru:
The dataset can be found at /nfs/semeru/semeru_datasets/code_xglue/code-to-code/code-refinement/data/medium in Semeru

## Task Definition

Code refinement aims to automatically fix bugs in the code, which can contribute to reducing the cost of bug-fixes for developers.
In CodeXGLUE, given a piece of Java code with bugs, the task is to remove the bugs to output the refined code. 
Models are evaluated by BLEU scores, accuracy (exactly match) and [CodeBLEU](https://github.com/microsoft/CodeXGLUE/blob/main/code-to-code-trans/CodeBLEU.MD).

## Dataset

We use the dataset released by this paper(https://arxiv.org/pdf/1812.08693.pdf). The source side is a Java function with bugs and the target side is the refined one. 
All the function and variable names are normalized. Their dataset contains two subsets ( i.e.small and medium) based on the function length. This dataset is medium.



### Data Statistics

Data statistics of this dataset are shown in the below table:

|          | #Examples |
| -------  | :-------: |
|          |   Medium  |
|  Train   |   52,364  |
|  Valid   |    6,545  |
|   Test   |    6,545  |

# Reference
<pre><code>@article{tufano2019empirical,
  title={An empirical study on learning bug-fixing patches in the wild via neural machine translation},
  author={Tufano, Michele and Watson, Cody and Bavota, Gabriele and Penta, Massimiliano Di and White, Martin and Poshyvanyk, Denys},
  journal={ACM Transactions on Software Engineering and Methodology (TOSEM)},
  volume={28},
  number={4},
  pages={1--29},
  year={2019},
  publisher={ACM New York, NY, USA}
}</code></pre>


