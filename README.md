<div align="center">
  <h1> Evaluating Open-QA Evaluation </h1>
  
  ![Data Version](https://img.shields.io/badge/Data%20Version-1.0.0-blue.svg?style=for-the-badge&logo=appveyor)
  [![License: Apache-2.0](https://img.shields.io/crates/l/Ap?style=for-the-badge)](https://opensource.org/licenses/Apache-2.0)
  [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=for-the-badge)](https://github.com/yafuly/DeepfakeTextDetect/issues)
</div>

# 📌 Table of Contents
- [Introduction](#-introduction)
- [Dataset](#-dataset)
- [License](#-license)
- [Citation](#-citation)
- [Contact](#-contact)
  
# 🚀 Introduction
  Welcome to our GitHub repository for the "Evaluating Open-QA Evaluation" [paper](https://arxiv.org/abs/2305.12421), a comprehensive study on the evaluating of evaluation methods in Open Question Answering (Open-QA) systems.
  
  Open-QA systems, which generate answers to questions with a vast range of possible topics, have become an increasingly significant research field in recent years. However, accurately evaluating these systems remains challenging, and currently lacks robust, reliable methods.
  
  In response to this, we introduce the QA Evaluation task (QA-Eval), a new task that rigorously tests various evaluation methods for their ability to accurately assess the relevance of machine-generated answers to a set of gold standard answers within an Open-QA context. This task requires the evaluating method to discern whether a machine-generated answer aligns with the gold standard answer, with performance evaluated against human-annotated results.
  
  We sourced our data from the test sets of two well-established QA datasets, Natural Questions (NQ) and TriviaQA. We ask several representative models, including FiD, ChatGPT-(3.5/4), GPT-3.5 and BingChat, to answer the questions. We then manually annotated the correctness of each question-answer pair.
  
  Through this work, we hope to foster a deeper understanding of Open-QA systems, their evaluations, and aid the research community in developing more reliable automatic evaluation tools.
  
# 📝 Dataset
  ## Data Description
  
  Each data point in our dataset is represented as a dictionary with the following keys:
```
  "question": The question asked in the Open-QA task.
  "golden_answer": The gold standard answer to the question.
  "answer_fid", "answer_gpt35", "answer_chatgpt", "answer_gpt4", "answer_newbing": The answers generated by different models (FiD, GPT-3.5, ChatGPT-3.5, GPT-4, and New Bing, respectively).
  "judge_fid", "judge_gpt35", "judge_chatgpt", "judge_gpt4", "judge_newbing": Boolean values indicating whether the corresponding model's answer was judged to be correct or incorrect (True for correct, False for incorrect) by human.
  "improper": Boolean flag indicating whether the question was inappropriate or not (True for inappropriate, False for proper).
```
  Here is an example of a data point:
```json
{
  "question": "who got the first nobel prize in physics",
  "golden_answer": "Wilhelm Conrad R\u00f6ntgen",
  "answer_fid": "Wilhelm R\u00f6ntgen",
  "judge_fid": true,
  "answer_gpt35": "The first Nobel Prize in Physics was awarded to Wilhelm R\u00f6ntgen in 1901.",
  "judge_gpt35": true,
  "answer_chatgpt": "The first Nobel Prize in Physics was awarded in 1901 to Wilhelm R\u00f6ntgen for his discovery of X-rays.",
  "judge_chatgpt": true,
  "answer_gpt4": "The first Nobel Prize in Physics was awarded in 1901 to Wilhelm Conrad R\u00f6ntgen, a German physicist. He received the prize for his discovery of X-rays, a groundbreaking achievement that revolutionized the fields of medicine, physics, and chemistry.",
  "judge_gpt4": true,
  "answer_newbing": "According to Wikipedia,Wilhelm Conrad R\u00f6ntgen of Germany got the first Nobel Prize in Physics in 1901 for his discovery of X-rays.  He received 150,782 SEK (Swedish krona) as the prize money.",
  "judge_newbing": true,
  "improper": false
}
```
  ## Data Scale
  The scale of our dataset is detailed in the table below:
  
 |models | Natural Questions| TriviaQA |
 |------------------------------|------------------------------|------------------------------|
 |DPR+FiD |3610|2000|
 |GPT-3.5 |3610|2000|
 |ChatGPT-3.5 |3610|2000|
 |ChatGPT-4 |3610|2000|
 |Bing Chat |3610|2000|
 
# 📜 License

This dataset is released under the [Apache-2.0 License](LICENSE).

# 📚 Citation

If you use this dataset in your research, please cite it as follows:
```bibtex
@inproceedings{
  wang2023evaluating,
  title={Evaluating Open-{QA} Evaluation},
  author={Cunxiang Wang and Sirui Cheng and Qipeng Guo and Yuanhao Yue and Bowen Ding and Zhikun Xu and Yidong Wang and Xiangkun Hu and Zheng Zhang and Yue Zhang},
  booktitle={Thirty-seventh Conference on Neural Information Processing Systems Datasets and Benchmarks Track},
  year={2023},
  url={https://openreview.net/forum?id=UErNpveP6R}
}
```
## 📮 Contact
We welcome contributions to improve this dataset! 
If you have any questions or feedback, please feel free to reach out at wangcunxiang@westlake.edu.cn.
