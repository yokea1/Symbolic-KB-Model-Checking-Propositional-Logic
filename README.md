# Symbolic KB & Model Checking — Propositional Logic  
# 符号知识库与模型检验 — 命题逻辑

## 📘 Overview | 项目简介
This project implements a **Propositional Logic Knowledge Base (KB)** and a **Model Checking** mechanism in Python.  
The goal is to represent symbolic logic statements, build a knowledge base, and verify logical entailment between propositions.  

本项目使用 Python 实现了一个**命题逻辑知识库 (Knowledge Base)** 与**模型检验 (Model Checking)** 系统。  
旨在通过符号逻辑的方式表达命题、构建知识库，并验证命题之间的逻辑蕴涵关系。

---

## 🧩 Features | 功能特性
- Define propositional symbols (e.g., Storm, Darkseid, Lex).  
- Construct complex formulas using logical connectives (¬, ∧, ∨, →, ↔).  
- Combine multiple sentences into a knowledge base (KB).  
- Use `model_check()` to verify whether a statement logically follows from the KB.  
- Demonstrate reasoning through a superhero scenario (Superman, Darkseid, Lex Luthor).  

- 支持定义命题符号（如 Storm、Darkseid、Lex）。  
- 可使用逻辑连接词（非、与、或、蕴涵、等价）构建复合命题。  
- 将多条逻辑语句组合成一个知识库 (KB)。  
- 使用 `model_check()` 检验目标命题是否能从 KB 推导得出。  
- 通过“超人 vs Darkseid vs Lex”的场景演示逻辑推理。

---

## 🧠 Example Code | 示例代码

```python
from logic import *

# Define symbols
S = Symbol("storm")
D = Symbol("darkseid")
L = Symbol("lex")

# Define knowledge base
kb = And(
    Implication(Not(S), D),
    Or(D, L),
    Not(And(D, L)),
    L
)

# Query the model
print("KB formula:", kb.formula())
print("Is it storming today?", model_check(kb, S))
print("Is Superman fighting Darkseid today?", model_check(kb, D))
print("Is he NOT fighting Lex Luthor today?", model_check(kb, Not(L)))
print("Is it storming OR Darkseid today?", model_check(kb, Or(S, D)))
print("Is it storming AND Lex is present?", model_check(kb, And(S, L)))
📊 Sample Output | 示例输出
vbnet
Copy code
KB formula: (((¬storm → darkseid) ∧ (darkseid ∨ lex)) ∧ ¬(darkseid ∧ lex) ∧ lex)
Is it storming today?  False
Is Superman fighting Darkseid today?  True
Is he NOT fighting Lex Luthor today?  False
Is it storming OR Darkseid today?  True
Is it storming AND Lex is present?  False
🧱 Project Structure | 项目结构
bash
Copy code
├── logic.py                # Core logic module (Symbol, And, Or, Not, etc.)
├── model_checking.py       # Model checking implementation
├── main.py                 # Demo script for reasoning and testing
└── README.md               # Project documentation (this file)
🧰 Technologies | 技术栈
Language: Python 3

Core Concepts: Propositional Logic, Knowledge Representation, Model Checking

Library: Custom logic.py module (based on MIT AI logic framework)

🧑‍💻 Author | 作者
He Yuke (何昱柯)
Software Engineering, UPM
Email: heyukeyoke@gmail.com

📚 Learning Outcome | 学习成果
Gained hands-on understanding of knowledge representation and logical reasoning.

Implemented a symbolic inference engine to test logical entailment.

Strengthened understanding of propositional logic semantics and truth evaluation.

深入理解了知识表示与逻辑推理的实现原理。

实现了一个可进行命题蕴涵检验的符号推理引擎。

强化了对命题逻辑语义与真值评估的理解。


