---
permalink: /
title: "Junteng Liu"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

## About Me

Hi, I'm **Junteng Liu** (刘俊腾). I'm a first-year PhD candidate at the **HKUST NLP Group**, Hong Kong University of Science and Technology (HKUST), advised by **Professor Junxian He**. I completed my B.Eng. at **Shanghai Jiao Tong University (SJTU)** in June 2024.

My research focuses on **natural language processing** and **machine learning**. Specifically, I am interested in:

- **LLM Reasoning and Reinforcement Learning** — Developing reasoning capabilities in large language models
- **Hallucination in Vision-Language Models (VLM)** — Understanding and mitigating hallucinations in multimodal models
- **LLM Truthfulness and Interpretability** — Making LLMs more truthful and their decisions more interpretable

I have received the **Zhiyuan Honor Scholarship** at Shanghai Jiao Tong University.

## Academic Background

- **Ph.D. in Computer Science** (2024–Present) — Hong Kong University of Science and Technology (HKUST)
- **B.Eng. in Computer Science** (2020–2024) — Shanghai Jiao Tong University (SJTU)

## Research Experience

**Research Intern** | MINIMAX
*February 2025 – Present*

**Research Intern** | Tencent WXG
*June 2024 – September 2024*
  - Advisor: Zifei Shan

**Research Intern** | Shanghai AI Lab
*June 2023 – December 2023*
  - Advisor: Prof. Yu Cheng

## Publications

{% for pub in site.publications reversed %}
  {% if pub.category == 'conferences' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

### Preprints

{% for pub in site.publications reversed %}
  {% if pub.category == 'preprints' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

## Skills

- **Programming Languages:** Python, C/C++, Shell, LaTeX
- **Deep Learning Frameworks:** PyTorch, TensorFlow
- **NLP & ML:** Large Language Models, Reinforcement Learning, Vision-Language Models, Hallucination Detection, Model Interpretability
- **Tools:** Git, Linux, Docker

## Contact Information

- **Email:** [jliugi@connect.ust.hk](mailto:jliugi@connect.ust.hk)
- **GitHub:** [Vicent0205](https://github.com/Vicent0205)
- **Google Scholar:** [Junteng Liu](https://scholar.google.com/citations?hl=en&user=tbK9jl4AAAAJ&view_op=list_works&sortby=pubdate)
- **X (Twitter):** [@junteng88716710](https://x.com/junteng88716710)
