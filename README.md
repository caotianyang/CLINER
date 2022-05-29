# CLINER
data &amp; code for paper "CLINER: Clinical Interrogation Named Entity Recognition"
## Dataset and Annotation

In  this  section,  we elaborate on our dataset and the annotation procedure. Our dataset originates from a Chinese online health community,[chunyuyisheng](https://www.chunyuyisheng.com/). Our dataset will be released upon acceptance.} where patients can submit their health problems and then doctors kick off a conversation to communicate with the patients and provide professional suggestions. Compared to conventional NER datasets, our proposed dataset focuses on medical dialog text along with massive domain-specific items appearing in the text. It is a more challenging benchmark dataset since there are plenty of colloquial expressions amongst the dialog, which could be also annotated as entities. The dataset contains 5 categories, 72 types of entities as well as 3 types of states. Each entity is associated with a state and two labels with the same entity but different states are considered as different rather than progressive. 

The most frequent types include *symptom:hyperglycemia, symptom:arrhythmia*, and so on. The detailed top-20 frequent labels can be found in [Fig.2](figs/data.jpg)
