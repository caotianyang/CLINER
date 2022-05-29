# CLINER
data &amp; code for paper "CLINER: Clinical Interrogation Named Entity Recognition"

## Dataset and Annotation

In  this  section,  we elaborate on our dataset and the annotation procedure. Our dataset originates from a Chinese online health community,[chunyuyisheng](https://www.chunyuyisheng.com/). Our dataset will be released upon acceptance.} where patients can submit their health problems and then doctors kick off a conversation to communicate with the patients and provide professional suggestions. Compared to conventional NER datasets, our proposed dataset focuses on medical dialog text along with massive domain-specific items appearing in the text. It is a more challenging benchmark dataset since there are plenty of colloquial expressions amongst the dialog, which could be also annotated as entities. The dataset contains 5 categories, 72 types of entities as well as 3 types of states. Each entity is associated with a state and two labels with the same entity but different states are considered as different rather than progressive. 

The most frequent types include *symptom:hyperglycemia, symptom:arrhythmia*, and so on. The detailed top-20 frequent labels can be found in [Fig.2](datset.jpg)

### Table 1
|     | **Train**  | **Dev** | **Test** | **Total** |
|  ----  | ----  | ---- | ---- | ---- |
|   Interrogation dialog  | 3633  | 756 | 685 | 5074 |
|   Window  | 6746  | 1410 | 1354 | 9510 |
|   NER label   | 7853 | 1765 | 1551| 11169 |
|   MIE label   | 6887 | 1513 | 1371 | 9771 |
|   Updated state   | 1686 | 337 | 277 | 2300 |

As shown in Table 1, our dataset includes 5,074 clinical interrogation text dialog along with 11,169 NER labels and 9,771 MIE labels. The train/dev/test is splited as listed in Table 1. Since we focus on the transition of states for each label, we also count the number of states being updated, which are 2,300 in our dataset.  Due to the inherent data imbalance problem, 21 of its 72 entity types only have fewer than 10 annotated instances.

An important characteristic of our dataset is that we take into consideration the fact that the state of entities may be changed along with the clinical interrogation.
Based on our observation to the real data, the updating rules are complex and can't be listed with a finite set. We thus summarize our annotation schema as follows: 1) entity state in current window is implicitly related to both following and above window context. 2) entity state is not always updated with contextual information, e.g., above dialog turns make hypothetical description of the entity, which is redundant for state prediction. 3) state "unknown" aren't supposed to affect state "positive" and "negative", while the state transformation between "positive" and "negative" requires checking specific context. 

Based on the criteria above, we invite six outsourcing staffs with medical background to participate in the dataset construction process. They cross-annotated each conversation and assigned the pre-defined labels to each entity by taking the whole dialog into account. If one entity was annotated differently by two annotators, the third annotator would be invited and give a final decision.
