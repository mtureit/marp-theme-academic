---
marp: true
theme: academic-tml
paginate: true
math: katex
---

<!-- _class: lead -->

# Self-Introduction & Research Plan at HCMUT

**Eita Matsuura**
GD1, Science of Technology Innovation (Year 1 of 5-year Integrated Doctoral Program)
Theory of Machine Learning Laboratory (TML Lab)
Nagaoka University of Technology

May 2026

---

## About Me

### Eita Matsuura (松浦 瑛太)

<div class="two-columns">
<div class="column">

**Program:**
- 5-year Integrated Doctoral Program, Science of Technology Innovation (GD1, equivalent to M1)

**University:**
- Nagaoka University of Technology

**Lab:**
- Theory of Machine Learning Laboratory

**Supervisor:**
- Assoc. Prof. Gendo Kumoi

</div>
<div class="column">

**Research Interest**
- Effectiveness evaluation of a generative-AI career-education support system for high school students

**Hobbies**
- Finding good restaurants
- Reading manga

</div>
</div>

---

## Background: Existing Research

### Two known phenomena motivating my research

**1. LLM low-diversity problem**
- LLMs produce low-variance responses by default
- Cannot reproduce the diversity of real human decision-making

**2. Foreign Language Effect** (Keysar et al., 2012)
- People's decision-making changes between their L1 and L2
- A well-documented cognitive bias in human studies

<div class="bubble">

**Open question:** Does the Foreign Language Effect propagate into LLM-based simulation of human decision-making?

</div>

---

## My Research at HCMUT

### Research Topic

**Evaluating LLM Simulation Diversity with Real Decision-Making Styles under Japanese–Vietnamese × L1/L2 Cross-Cultural Conditions**

### Methodology: Culture × Language 2×2 Design

|                   | Style doc from JP participants | Style doc from VN participants |
|:---|:---:|:---:|
| **Interview in L1** | ① JP × Japanese (L1)         | ② VN × Vietnamese (L1)        |
| **Interview in L2** | ③ JP × English (L2)          | ④ VN × English (L2)           |

- Per condition: **3 tasks × 3 LLMs** full factorial experiment
- **Evaluation metric:** <span class="marker">Multilingual Vendi Score</span> (diversity)
- **Participants:** N=15 Japanese (NUT) + N=15 Vietnamese (HCMUT)

---

## Research Plan

### 3-Phase Research Plan

| Phase   | Period          | Location        | Key Activities                                                                   |
|:---|:---|:---|:---|
| Phase 1 | – Aug 2026      | Japan (NUT)     | JP data (N=15, L1/L2 pairs); build multilingual Vendi Score framework            |
| Phase 2 | Sep – Nov 2026  | Vietnam (HCMUT) | VN data (N=15, VN/EN pairs); JP×VN × L1/L2 × 3 tasks × 3 LLMs experiment         |
| Phase 3 | Dec 2026 –      | Japan (NUT)     | 4-condition cross-analysis; culture/language invariant extraction; paper writing |

**Expected outputs:**
- JP–VN × L1/L2 paired style-document corpus (N=30, open on GitHub)
- Multilingual Vendi Score framework (OSS)
- International co-authored paper

---

## Collaboration Request

### What We Need from HCMUT

1. **Participant Recruitment** — ~N=15 Vietnamese participants
   - Style documents collected via AI interviews in Vietnamese (L1) + English (L2)
2. **Your Support** — We warmly welcome any collaboration and support from Prof. Tho's laboratory in making this research a success.

---

<!-- _class: lead -->

# Thank You for Listening!

**Eita Matsuura**
Theory of Machine Learning Laboratory (TML Lab)
Nagaoka University of Technology
