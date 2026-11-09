---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

A current copy of my full CV is available here: **[Appau_Gideon_CV.pdf](/files/Appau_Gideon_CV.pdf)**

Education
======
* M.S. in Software Engineering (AI/ML), University of Science and Technology of China, 2024 - 2027 (expected)
  * Thesis: *Class-Adaptive Focal Sharpness-Aware Minimization for Long-Tailed Visual Recognition*. Advisor: [Assoc. Res. Pengkun Wang](http://home.ustc.edu.cn/~pengkun/index.html).
* B.Sc. in Information Technology Education, University of Education, Winneba, Ghana, 2018 - 2022
  * First Class Honours, Top 10%. Advisor: Dr. William Asiedu.

Work experience
======
* 2025 - Present: Graduate Researcher
  * University of Science and Technology of China, Suzhou, China
  * Proposed CA-Focal-SAM, a class-adaptive sharpness-aware minimization optimizer that improves tail-class accuracy by 6.03% on CIFAR-10-LT (IR=200) with no architectural change or inference overhead; designed GammaAdaptor (2 learnable scalars) mapping class frequency to per-class focal parameters, and a quadratic perturbation-radius curriculum verified by Hessian spectral analysis.
  * Proposed SFCA (Sharpness-Feedback Classwise Allocation), a closed-loop online controller that reallocates per-class sharpness using live geometric feedback; under a pre-specified falsification protocol (polarity under two outer losses, signal-destruction controls, hindsight-oracle bound, class-level regression) the feedback channel carried no measurable information - a rigorous negative boundary result. The frozen scarcity-prior controller improves CIFAR-100-LT tail accuracy over Focal-SAM by +2.50 points at IR=100 and +1.98 points at IR=200 (4 fixed seeds each, zero inference overhead).
  * Multi-seed statistical protocol (~200 runs, uniform recipe, 4 seeds at IR=100/200) on CIFAR-100-LT; ImageNet-LT and Places-LT as exploratory screens; 20+ qualitative analyses (t-SNE, 2D/3D loss landscapes, confusion matrices).

* Mar 2026 - Apr 2026: Machine Learning Intern
  * Future Interns (remote)
  * End-to-end time-series forecasting (6-month sales prediction); NLP ticket-classification pipeline with BERT/DistilBERT and sentiment-based priority routing; AI recruitment tool combining spaCy/NLTK resume parsing with LLM-based job matching.

* Nov 2022 - Aug 2023: IT Assistant
  * Akenten Appiah Menkah University, Kumasi, Ghana
  * Automated data workflows in Python (Pandas, NumPy), cutting manual processing time by 40%; optimized SQL databases with 5,000+ records, improving query performance by 30%.

* Aug 2021 - Mar 2022: Full-Stack Web Developer Intern
  * Amidarr A-mole, Ghana
  * Engineered 3 full-stack web applications (Flask, JavaScript, MySQL); integrated the PayStack payment API into an e-commerce platform.

Skills
======
* Languages: Python, JavaScript, SQL, Java, Bash
* ML/AI: PyTorch, scikit-learn, Transformers, LangChain, LangGraph, Ollama, AutoGen, FAISS, Chroma
* LLM/NLP: BERT, DistilBERT, spaCy, NLTK, RAG agents
* Data: Pandas, NumPy, Matplotlib, feature engineering, time-series forecasting
* Web & Tools: Flask, REST APIs, Gradio, MySQL, Git, Linux, Docker, LaTeX

Publications
======
None yet; thesis manuscripts in preparation.
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Awards
======
* Chinese Government Scholarship (CSC), USTC, 2024
* First Class Honours, Top 10%, University of Education Winneba, 2022
* NVIDIA LLM RAG Agent Fundamentals, 2025
* DeepLearning.AI Advanced Learning Algorithms, 2025
* DeepLearning.AI Supervised Machine Learning: Regression & Classification, 2025
