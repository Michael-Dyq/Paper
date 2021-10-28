# Paper

**Content**

[//]: <              - ** **  [[ ]](https://)                   >
# Event
## Year 2020
- **Zero-shot Label-Aware Event Trigger and Argument Classification**  [[Hongming Zhang, Haoyu Wang, Dan Roth]](https://cogcomp.seas.upenn.edu/page/publication_view/942)
  - **Goal:**  
     Proposed a zero-shot event extraction approach, which first identifies events with existing tools (e.g., SRL) and then maps them to a given taxonomy of event types in a zero-shot manner. 
  - **Core Method:**
    1. Event Identification：find event triggers by the SRL models and classify whether triggers belong to the pre-defined event ontology or not (classification task)
    2. Represent the labels with a cluster of contextualized embeddings (rather than just words). More specially, select several sentences that contain the word “attack” from an          external corpus (e.g., New York Times (NYT)). Use a pre-trained language model (e.g., BERT (Devlin et al., 2019)) to get the word embedding as a data point in the “attack"        cluster.
    3. At the inference time, acquire the contextualized representation of identified triggers and arguments, and map them to their corresponding types based on their  
       similarities to those clusters in the embedding space.
    4. Beyond the labels, event definitions also provide constraints between types and roles. For example, the role “Attacker” can only appear as an argument of “Conflict:Attack” rather than “Life:Marry,” and only a person or a nation can take the role of an “Attacker".  These constraints to regularize the zero-shot model by formulating as an integer linear programming (ILP) (Roth and tau Yih, 2004) and only produce decisions that satisfy all the constraints.
   
  - **Achievement:**
    1. Map 83% of the triggers and 54% of the arguments to correct types, almost doubling the performance of the previous best zero-shot event classification approach
    2.  When pipelined with our improved zero-shot identification step, we exhibit an zero-shot event extraction pipeline that rivals a SOTA supervised system (Lin et al., 2020)   trained on over 6,000 sentences.


   - **Data Source:**
     1. ACE-2005, which has 33 event trigger types and 22 argument role types. 
 


# Temporal
## Year 2021

- **Temporal Reasoning on Implicit Events from Distant Supervision (NAACI)**  [Ben Zhou, Kyle Richardson, Qiang Ning, Tushar Khot, Ashish Sabharwal1, Dan Roth](https://arxiv.org/abs/2010.12753)   Git [repository](https://github.com/allenai/tracie)
   - **Abstract:**  
    Propose a neuro-symbolic temporal reasoning model, SYMTIME, which exploits distant supervision signals from large-scale text and uses temporal rules to combine start times and durations to infer end times. Introduce a new dataset **TRACIE** (TempoRAL Closure InfErence) foucses on temporal relations on implicit events in short stories.
   - **Core Methods:**
     1. Use T5-Large fine-tuned on TRACIE to achieve binary prediction accuracy of 67.9% as baseline.
     2. Propose a novel distant supervision technique that improves generalization by extracting temporal patterns in large-scale free text as part of an additional pre- training step. Use large windows of text such as paragraphs in contrast to sentence level. Result a mode PINTIME(Pattern-Time) achieving 76.6% on TRACIE.
     3. Couple PTNTIME with a duration model from Zhou et al. (2020) to create a neural-symbolic reasoning model called SYMTIME, which achieves 78.9% on TRACIE.


- **Conditional Generation of Temporally-ordered Event Sequences**  [Shih-Ting Lin et al.](https://arxiv.org/abs/2012.15786)   Git [repository]

   - **Abstract:**  
    Proposes a single model of events to suupport inferenes in two tasks: (1) temporal event ordering; (2)event infilling or inferring unseen or unmentioned event infilling.
   - **Core Methods:**
     1. Take temporally-ordered event sequences, shuffle them, delete some events, and then attempt to recover the original event sequence. 
     2. BART-based model.
     3. 

   - **Evaluation Methods and Data Source:**
   - 1. EventsNarrative Dataset. (Training). Assuming discourse order reflect temporal order.
   - 2. CaTeRS. (Evaluation). Used for both temporal relations and event infilling evaluation.
   - 3. MCTaco. (Evaluation). For temporal relations evaluation.
   - 4. BERT-based pairwise model and BERT-based pointerr network are used as comparison for temporal ordering task.
   - 5. GPT-2 baselines is used as comparison for infilled events generation task.

## Before Year 2017
Context-dependent Semantic Parsing for Time Expressions

- **Context-dependent Semantic Parsing for Time Expressions (ACL 2014)** [Kenton Lee, etc.](https://aclanthology.org/P14-1135.pdf)
   - **Abstract:** 
     The goal is to find all time expressions in an input document. Problem is devided into two parts: detection and resolution(normalization). Make use of a hand-engineered Combinatory Categorial Grammar (CCG) to construct a set of meaning representations that identify the time being
described. 
   - **Core Methods:**
   - **Achievement:**
   - **Data Source:**
      
