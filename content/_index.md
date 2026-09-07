---
title: Appau Gideon Kofi Amo
type: landing-page

sections:
  # PhD Banner
  - block: hero
    content:
      title: 🎓 Seeking PhD Opportunities in Computer Science & AI — Fall 2027
      text: |
        Fall 2027 intake. Interested in reinforcement learning, world models & embodied AI,
        efficient optimization for visual recognition, and LLM agents.
        <a href="mailto:gideonamoappau@mail.ustc.edu.cn">Get in touch →</a>
      cta:
        url: mailto:gideonamoappau@mail.ustc.edu.cn
        label: Contact Me

  # About / Biography (name, avatar, bio, education, interests + CV download)
  - block: resume-biography-3
    id: about
    content:
      username: me
      text: ''
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md
      avatar:
        size: medium
        shape: circle

  # Research Vision
  - block: markdown
    id: vision
    content:
      title: Research Vision & PhD Goals
      text: |
        I aim to develop **embodied agents that learn continuously from interaction** —
        systems that combine the reasoning power of large language models with the grounded
        decision-making of reinforcement learning.

        ### Specific Research Directions
        - **RL for LLM Reasoning:** Train language models to reason through verifiable rewards (GRPO, PPO).
        - **Continual & Lifelong RL:** Design agents that learn new tasks sequentially without forgetting.
        - **Embodied AI & Robotics:** Bridge high-level LLM reasoning with low-level robotic control.
        - **Multi-Agent Coordination:** Decentralized systems with economic incentives and reputation.

  # Projects Grid
  - block: portfolio
    id: projects
    content:
      title: Selected Projects
      filters:
        folders:
          - projects
      sort_by: Date
      sort_ascending: false

  # Publications
  - block: collection
    id: papers
    content:
      title: Publications
      filters:
        folders:
          - publications
      count: 5
    design:
      view: citation

  # Blog Posts
  - block: collection
    id: blog
    content:
      title: Blog
      filters:
        folders:
          - blog
      count: 5

  # Experience Timeline
  - block: experience
    id: experience
    content:
      title: Experience
      date_format: Jan 2006

  # Skills
  - block: features
    id: skills
    content:
      title: Technical Skills
      items:
        - name: Python
          icon: code
          description: PyTorch, scikit-learn, Transformers
        - name: Agent Frameworks
          icon: robot
          description: LangChain, LangGraph, AutoGen
        - name: RL & LLMs
          icon: brain
          description: DQN, PPO, GRPO, RLHF
        - name: Cloud & GPU
          icon: server
          description: AutoDL, Docker, Remote GPU servers

---
