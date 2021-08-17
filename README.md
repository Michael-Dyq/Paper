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

- **Temporal Reasoning on Implicit Events from Distant Supervision (NAACI)**  [Ben Zhou, Kyle Richardson, Qiang Ning, Tushar Khot, Ashish Sabharwal1, Dan Roth](https://arxiv.org/abs/2010.12753) git[https://github.com/allenai/tracie]
  - **Goal:**
    Propose a neuro-symbolic temporal reasoning model, SYMTIME, which exploits distant supervision signals from large-scale text and uses temporal rules to combine start times and durations to infer end times.
   - **Core Method:**
     1. 
