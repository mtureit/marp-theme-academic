---
marp: true
theme: academic-tml
paginate: true
math: katex
---

<!-- _class: lead -->

# HCMUT Collaboration: Cross-Lingual Opinion Strength Study

### 3-Month Preparation Roadmap

**Eita Matsuura**
Supervisor: Assoc. Prof. Gendo Kumoi
Theory of Machine Learning Laboratory (TML Lab)
Nagaoka University of Technology

June 2026

---

## Research Overview

### The Core Question

<div class="bubble">

**Core question:** When the same person discusses the same topic in Japanese, English, and Vietnamese, how do their <span class="marker">opinion strength</span> and <span class="marker">argumentative consistency</span> change?

</div>

**Approach:**
- **Live API** (Gemini, voice-dialogue AI) for adaptive interviewing
- Within-subject design across 3 language conditions

---

## Why This Study?

### Three Gaps in Prior Work

**1. Limitations of existing methods**
- Only static translated questionnaires
- No flexible Q&A possible

**2. Zero literature on FLE in Vietnamese speakers**
- The Foreign Language Effect has never been tested with VN speakers

**3. No prior JA–EN–VI trilingual comparison**

<div class="bubble">

Live API enables response-contingent follow-up → opinion strength can be extracted from naturalistic dialogue.

</div>

---

## Two Core Metrics

### Definitions and Measurement

| Metric | Definition | How to Measure |
|:---|:---|:---|
| **Opinion Strength** | Certainty, assertiveness, resistance to counter-arguments | Hedge-word frequency · prosodic features (eGeMAPS) · stance retention after rebuttal |
| **Argumentative Consistency** | Stance and premises remain stable across languages | LaBSE multilingual embedding cosine similarity · binary stance agreement rate |

---

<!-- _class: compact -->

## Study Design

### Participants, Procedure, Topics

**Participants:**
- JA–EN bilinguals: NUT students
- JA–EN–VI trilinguals: HCMUT students

**Procedure:**
- Adaptive Live API interview on the same topic in each language
- Language presentation order is <span class="marker">counterbalanced</span>

**Design:**
- <span class="marker">Within-subject</span> (same individual across all language conditions)

**Topics:**
- Educational and social topics relevant to multicultural co-learning

---

## Application

### Why This Matters in Practice

<div class="bubble">

Before multicultural co-learning discussions, run a <span class="marker">pre-discussion interview</span> to obtain each student's <span class="marker">cross-lingual opinion profile</span> → use it as input for optimal group formation (proof-of-concept).

</div>

**Goal:**
- Combine students with diverse opinion strengths and argumentation styles
- Propose group compositions that improve discussion quality

---

## Publication Strategy

### Target Venues

| Venue | Character | Acceptance | APC |
|:---|:---|:---:|:---:|
| **IEEE Access** (first choice) | Applied focus, technical soundness | ~27–28% | $2,160 |
| IEEE Trans. Affective Computing | Computational study of emotion/certainty/voice | Stricter | Higher |

**Three essentials for IEEE Access acceptance:**

1. Reproducible system implementation (code release)
2. Novel multilingual dataset (audio + transcript + annotation)
3. Metric validity verification

---

<!-- _class: compact -->

## Month 1 (June): Literature Reading

### Must-Read Papers

**① Foreign Language Effect — Foundations**
- Costa et al. (2014). *Your morals depend on language.* PLOS ONE
- Keysar, Hayakawa & An (2012). *The Foreign-Language Effect.* Psych. Sci.
- Circi et al. (2021). *Meta-analysis of FLE in decision-making.* PB&R

**② Cultural Frame Switching**
- Ramírez-Esparza et al. (2006). *Do bilinguals have two personalities?* JRP

**③ Voice & Certainty Quantification**
- Eyben et al. (2015). *eGeMAPS.* IEEE T. Affective Computing

**④ Adaptive AI Interviewing**
- Wuttke et al. (2024). *AI Conversational Interviewing.* arXiv:2410.01824

**⑤ Group Formation (Application Background)**
- Minimum Entropy Collaborative Groupings (2023). PLOS One

---

## Month 1: Tasks

### Concrete Deliverables

- Each member reads an assigned paper and produces a **1-page A4 summary** (JA or EN)
- **Collaborative glossary**: confirm Opinion Strength · Argumentative Consistency · FLE · CFS · within-subject in JA / EN / VI
  - Intent: avoid translation drift; ensure consistent terminology across participant briefings, protocols, and the paper
- **Run a Gemini Live API demo** (Hello-World level)
- **Think of 3 candidate discussion topics** suitable for multicultural co-learning

---

<!-- _class: compact -->

## Month 2 (July): System Design

### Additional Reading & Tasks

**Additional papers:**
- Stab & Gurevych (2017). *Parsing Argumentation Structures.* Comp. Linguistics
- Qi et al. (2023). *Cross-Lingual Consistency of Factual Knowledge.* arXiv:2310.10378
- Vietnamese politeness studies (face, indirect expression)

**Tasks:**
- **Interview protocol design**: follow-up logic, rebuttal timing, language-switch procedure
- **Live API implementation sketch**: WebSocket, VAD, session management, logging
- **Hedge-word correspondence table** (JA: 〜と思います / EN: I think / VI: tôi nghĩ, etc.)
- **IRB preparation**: voice-recording / personal-information consent drafts 

---
<!-- _class: compact -->

## Month 3 (August): Pilot & Validity

### Pilot Run & Validity Check

**Additional reading:**
- Bilingualism: Language and Cognition. *Resisting persuasion in cases of ideological conflict.* (basis for rebuttal-follow-up design)

**Tasks:**
- **Pilot run**: 5–10 JA–EN bilinguals (NUT side) through the full pipeline
- **Human annotation**: agreement between automatic and human ratings (<span class="marker">redesign metrics if Cohen's κ &lt; 0.4</span>)
- **Vietnamese ASR accuracy pre-measurement**: measure Gemini Live API VN recognition rate
- **Complete data pipeline**: audio → Whisper → feature extraction → scoring → visualization
- **HCMUT briefing slides** (English & Vietnamese) finalized before departure

---

## Tentative Roles

### NUT × HCMUT Division of Labor

| Role | NUT side | HCMUT side |
|:---|:---|:---|
| System implementation | Eita | — |
| JA / EN protocol design | NUT students | — |
| VN protocol & translation review | — | HCMUT students |
| Data annotation (VN) | — | HCMUT students |
| Statistical analysis | Eita | — |
| Paper writing | Kumoi (lead) | Co-author |

---
<!-- _class: compact -->

## Key Risks & Mitigations

### Four Risks to Watch

**① Vietnamese ASR accuracy**
- Live API quality is highest in English → measure VN rate in Month 3, log error rate as a control variable

**② FLE effect-size variability**
- g = 0.09–0.40 across prior studies → design with <span class="marker">null-result publishability</span> in mind

**③ Ethics review (IRB)**
- IRB · informed consent · anonymization · Google-API audio-transmission consent in both JP and VN

**④ Live API session limit**
- ~15-min session expiry → use <span class="marker">split-session design</span> for long interviews

---

## Next Steps

### Team Collaboration Plan

**June (Pre-investigation phase)**
- Eita's and Hieu's teams hold joint reading sessions on related papers to deepen understanding
- Both teams discuss and exchange ideas internally via **Slack**
- **Eita & Kei** support Khai and Hieu's research progress and provide tasks for the joint collaboration

**From July (Regular reporting phase)**
- Propose <span class="marker">bi-weekly meetings</span> with Prof. Tho
- The two teams will report progress to the professor **every 2 weeks** from early July

---

<!-- _class: lead -->

# Thank You for Listening!

### ご清聴ありがとうございました

**Eita Matsuura**
Theory of Machine Learning Laboratory (TML Lab)
Nagaoka University of Technology

Questions and comments welcome

---

<!-- _class: compact -->

## Appendix: Glossary 1

### Study Design & Ethics

**Counterbalance**
Systematically varying the presentation order of multiple conditions (3 languages here) across participants. Controls for order effects (fatigue, practice).

**Within-subject design**
A design where the same individual participates in all conditions. Removes individual-difference noise and achieves statistical power with fewer participants.

**Protocol**
A standardized procedure document for the interview. Greeting → question order → closing, written out so any interviewer can run the session identically.

**Informed consent**
An ethics procedure: fully explain the study's purpose, procedures, risks, and right to withdraw, and obtain written agreement from the participant.



---

<!-- _class: compact -->

## Appendix: Glossary 2-1

### Measurement, Statistics & Tech

**Human annotation**
Researchers manually assigning evaluation values to data. Used to validate the automatic metric.

**Cohen's κ (Kappa)**
A statistical measure of agreement between two raters (0 to 1). Below 0.4 indicates insufficient agreement (Landis & Koch, 1977).

**eGeMAPS**
A standard 88-feature set for extracting certainty, emotion, and speaking-style features from voice (Eyben et al., 2015). Used as the prosodic indicator for Opinion Strength.

**LaBSE**
Google's multilingual sentence-embedding model. Enables semantic similarity computation across languages. Used for Argumentative Consistency.

---

<!-- _class: compact -->

## Appendix: Glossary 2-2

### Measurement, Statistics & Tech

**ASR (Automatic Speech Recognition)**
Automatic speech recognition. The process by which Live API internally converts voice to text.

**null result**
A result where the predicted effect is not observed. This study is designed so that "opinions don't change across languages" is also a publishable, meaningful finding.
